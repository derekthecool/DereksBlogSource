---
title: "IncludeCsharpAndFsharpLibrariesInPowershell"
date: 2024-07-17T16:12:20
image:
categories:
  - powershell
  - csharp
  - fsharp
  - powershell-modules
draft: true
---

# Include Csharp And Fsharp Libraries In Powershell

Using compiled libraries from a csharp or fsharp project can provide a great
performance boost for powershell modules.
In fact, most of the built in powershell modules are compiled from csharp.

This guide is meant to help with getting started included compiled dotnet DLLs
(class libraries) into a powershell module.

## Ad hoc DLL Loading

Importing a dll is as simple as using the [Add-Type](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/add-type?view=powershell-7.4)

```powershell
# Check available commands from a nuget dll
[System.Reflection.Assembly]::LoadFrom("$HOME/.nuget\packages\google.protobuf\3.28.0\lib\net5.0\Google.Protobuf.dll").GetTypes()
```

Also shown on the Microsoft website is compiling csharp, then creating
powershell objects from the csharp class created.

```powershell
$Source = @"
public class BasicTest
{
  public static int Add(int a, int b)
    {
        return (a + b);
    }
  public int Multiply(int a, int b)
    {
    return (a * b);
    }
}
"@

Add-Type -TypeDefinition $Source
[BasicTest]::Add(4, 3)
$BasicTestObject = New-Object BasicTest
$BasicTestObject.Multiply(5, 2)
```

## Create A Powershell Module - The Easier Way

First things first you'll need to create a powershell module.
Create a new directory somewhere in your `$PSModulePath`

Easily check what paths you can use with this command

```powershell
$ENV:PSModulePath -split [IO.Path]::PathSeparator
```

- For Windows powershell 5.1 the most likely path to use would be
  `$HOME/Documents/WindowsPowerShell/Modules/`
- For powershell 7.4 use
  `$HOME/Documents/PowerShell/Modules/`

Then create a directory with the name you want for your powershell module
make a new dotnet class library.

```powershell
dotnet new classlib -o csharp_code

# Or with fsharp
dotnet new classlib --language=fsharp -o fsharp_code

# Publish the project
# This creates the release build and puts all DLLs into the source directory rather than relying on nuget cache
dotnet publish
```

Now in your powershell module manifest you can add the relative path to this
dotnet project in the RequiredAssemblies field in the `.psd1s`

```powershell
# Assemblies that must be loaded prior to importing this module
RequiredAssemblies = @(
    "csharp_code/bin/Release/net8.0/publish/csharp_code.dll",
    "fsharp_code/bin/Release/net8.0/publish/fsharp_code.dll"
)
```
