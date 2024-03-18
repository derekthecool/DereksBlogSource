---
title: 'Cmake Guide'
date: 2024-03-12T17:48:16
image: https://cmake.org/wp-content/uploads/2023/08/CMake-Logo.svg
categories:
  - 'C'
  - 'cmake'
draft: false
---

# Cmake Guide

{{< featuredImage alt="Cmake image" >}}

## Why Do We Need Cmake?

A build system to help manage dependencies, how to compile the project and other
items are the job of a project build system. However, the C programming language
is designed to work on nearly any hardware. So, the job of setting up the custom
project dependencies and compiling options has usually been on a per project
basis.

Thanks to cmake we can have sanity amidst the chaos! Here are the basic features
that cmake helps with:

- Multiple build project setup. The main idea behind cmake is to have a cross
  platform [make](https://www.gnu.org/software/make/) which is a Linux build
  tool that uses `makefile`'s to manage projects.
  Cmake works on many nearly every operating systems.
- Cross compiling. Need to build code on your machine designed for a different
  OS or even bare metal hardware? This is easy with cmake, you just need to
  specify a [toolchain file](https://cmake.org/cmake/help/book/mastering-cmake/chapter/Cross%20Compiling%20With%20CMake.html).
  As an embedded systems engineer, building code for another system is a daily
  task and cmake makes it possible. In fact the popular microcontrol series
  [ESP32 by Espressif](https://docs.espressif.com/projects/esp-idf/en/latest/esp32/api-guides/build-system.html)
  uses cmake as their build system.

## Getting Started Videos

I have found an awesome [YouTube video series by vector-of-bool](https://www.youtube.com/channel/UCkYGy96LXk3g-d6kP22aSDA/playlists)
that has been the most helpful resource for getting started.

Very useful blog post by [Dane Bulat](https://dane-bulat.medium.com/cmake-how-to-inspect-and-configure-the-compiler-877e6cb0317f)

## Install Latest Version Linux

Go to [Cmake website downloads page](https://cmake.org/download/)

## Setup Release And Debug Builds

It is very easy to setup different releases. [This stackoverflow](https://stackoverflow.com/questions/7724569/debug-vs-release-in-cmake)
page makes it clear.

## CMakeLists.txt Setup

## Subdirectory CMakeLists.txt Setup

I found this [StackOverflow reference](https://stackoverflow.com/questions/25609692/how-to-add-source-files-in-another-folder) to be the most helpful.
Just create a folder, put source files into it and then add a CMakeLists.txt file
there as well as the root. Make sure to have a line in the root file `add_subdirectory("src")`

## Main Commands

- To setup project with output going to a directory named build: `cmake -S . -B ./build`
- To build project without knowing what build syestem is used: `cmake --build ./build` where build is directory
