---
title: 'Cmake Guide'
date: 2024-03-12T17:48:16
image: https://cmake.org/wp-content/uploads/2023/08/CMake-Logo.svg
categories: ['c', 'cmake']
draft: false
---

# Cmake Guide

{{< featuredImage alt="Cmake image" >}}

## Personal Motivation

I am creating this guide because I really need and want to learn
Cmake. These are my reasons:

1. It is cross platform, this is essential for me
2. It will be the easiest way to manage my build for a work project at Freeeus.
   The project is called the FreeusAdapter and it is a C project for a mPERS
   device. It will need to a protobuf library called nanopb, started work on
   this project November 2020.

## CMakeLists.txt Setup

## Subdirectory CMakeLists.txt Setup

I found this [StackOverflow reference](https://stackoverflow.com/questions/25609692/how-to-add-source-files-in-another-folder) to be the most helpful.
Just create a folder, put source files into it and then add a CMakeLists.txt file
there as well as the root. Make sure to have a line in the root file `add_subdirectory("src")`

## Main Commands

- To setup project with output going to a directory named build: `cmake -S . -B ./build`
- To build project without knowing what build syestem is used: `cmake --build ./build` where build is directory
