---
title: 'C Programming'
date: 2024-03-12T17:48:16
image: https://upload.wikimedia.org/wikipedia/commons/archive/3/35/20220802133510%21The_C_Programming_Language_logo.svg
categories:
  - 'C'
draft: false
---

# C Programming

{{< featuredImage alt="C programming image" >}}

These notes are my working document to C programming. It includes basic concepts
and documentation on items of interest to me.

## Style

This nice embedded C coding
[standard](https://barrgroup.com/sites/default/files/barr_c_coding_standard_2018.pdf).
It really helps to use tools such as [clangformat](https://clang.llvm.org/docs/ClangFormat.html)
to help with automatic formatting.

## Libraries Vs Executables

They are essentially the same thing. However a library is meant to
be run by another program and a exectuable runs on its own.
For example the library <stdio.h> is a dynamic shared library. And
a simple hello world executable that just is meant to be run manually
would be an executable example.

Here are some helpful resources for this

- [StackOverflow](https://stackoverflow.com/questions/9688200/difference-between-shared-objects-so-static-libraries-a-and-dlls-so)
- [Look inside a shared library .so Linux with nm -D](https://stackoverflow.com/questions/38887351/how-can-i-look-inside-a-linux-so-or-a-object-and-see-what-functions-they-conta)
- [Unit testing with Ctest: Berts Blog](https://bertvandenbroucke.netlify.app/2019/12/12/unit-testing-with-ctest/)

## Static Libraries

### Linking Libraries

This [stackoverflow guide](https://stackoverflow.com/a/23621751) shows how to
link multiple static libraries together.

The command looks like this

```sh
ar -rcT libaz.a libabc.a libxyz.a

```

And luckily, it works just fine with the arm5 compiler

```sh
armar -rcT libaz.a libabc.a libxyz.a
```

## Cmake Build System

There is so much to Cmake that I will create a [new page](cmake.md) just for cmake.

### Shared Libraries

- [StackOverflow Guide on cmake Shared Libraries](https://stackoverflow.com/questions/17511496/how-to-create-a-shared-library-with-cmake)

## Macros!!

### Stringization And Double Stringization

Single stringization can be done with a macro like this. It can be used to get
the name of variables.

```c
#define S(x) #x

int world = 50;

// Print the name of the variable
printf("Hello " S(world)");

// output: "Hello world"
```

Double stringization can be done with created another macro additional to the
single stringization method. This can be used to stringize the value of the
variable instead of the name. Useful for integers.

```c
#define S(x) #x
#define xS(x) S(x)

int world = 50;

// Print the value of the variable
printf("Hello " Sx(world)");

// output: "Hello 50"
```

Here is an example where I used this to help create MQTT paths. I wanted to have
a macro for the QoS as a number and as the string form.

```c
#define BASE_PATH "ESP32_MQTT_TESTING/qos"
// Double "stringizing" trick to help append numeric macros with strings
#define S(x) #x
#define xS(x) S(x)

#define QoS0 0
#define QoS1 1
#define QoS2 2
#define TOPIC_PATH_QoS0 BASE_PATH xS(QoS0)
#define TOPIC_PATH_QoS1 BASE_PATH xS(QoS1)
#define TOPIC_PATH_QoS2 BASE_PATH xS(QoS2)

// this throws an error, because it is only single stringized
// #define TOPIC_PATH_QoS2 BASE_PATH S(QoS2)
```

## Embed Lua In C

Check out the full page [Using_C_With_Lua](Using_C_With_Lua.md)
