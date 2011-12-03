---
layout: post
title: First look at doom 3
---



## Why am I doing this?

I have always had an interest in reading code bases in languages that I don't use very often. C and C++ codebases are particular among these because they are languages I studied in school but never really used professionally and I always find it interesting to see what real world C and C++ looks like. I have also always had an interest in games and most of the games I love are written in C or C++ due to performance of the language when using Open-GL or DirectX.
You can imagine my delight then when the code for Doom 3 was finally made open source this week. I hurried over to the github repo and downloaded a copy to start to play. My original (and still current) intent for the code looks like this:

- Load the code in my IDE
- Build the code
- Run it with my Doom 3 pak files 
- Play with the game code a little to see how it works
- Understand as much as possible about the architecture of the engine


## Downloading the code

Downloading the code is pretty simple. The code was released into github and the original release can be found in [TTimos' Doom 3 repository](https://github.com/TTimo/doom3.gpl "Doom 3 repository"). github provides tons of information on how to download repositories using git or you can simply get a snapshot with no bindings [here](https://github.com/TTimo/doom3.gpl/zipball/master "TTimos doom 3 master zip download").

## Load the code

As a C# programmer by trade the fact that I use Visual Studio meant getting this code into my IDE was simple. The release comes with Visual Studio project files. In the neo directory when you get the code you will find the doom.sln file which is the solution for Visual Studio. When you load the solution there will be 7 projects grouped into 3 solution folders.

### libs
This contains 2 projects:

- idLib : A general purpose C++ lib made by Id. It seems to handle a lot of the same things you would find in the stl, like containers. It also has facilities for math, geometry, text parsing and bounding volumes.
- CurlLib : This seems to be a copy of the curl library. Curl is a library that allows you to do data transfer over various protocols like http.

### exes
These are the projects that produce executables

- DoomDLL : This project contains the entry point for the game and a lot of the framework for the engine. This will be what you run to debug etc.
- TypeInfo : This executable seems to parse the source code of the game and create a header file that contains all the constants and classes etc it finds in those files. This header is used in the game dll it seems. (Still looking into this and why its done)

### dlls
These are the game logic dlls and one other

- Game : Doom 3 :D Contains the definitions for the game entities, animations, AI and other goodness.
- Game-d3xp : The Doom 3 expansion dll. This seems to be a superset of the Game dll with the expansion stuff added. (I unloaded this project)
- MayaImport : A tool written to import maya resources into the doom 3 formats. (I use blender for 3d so, unloaded...)

## Building the code

Working on it :)