# C++ & OpenGL VSCode Setup
Thank you for visiting the page for my C++ & OpenGL visual studio code project setup. As the title says this is a setup, there is nothing special about this project other than that you can use it to have a base in OpenGL programming.

**Warning:** this readme file does assume that you have some experience with Visual Studio Code, g++ and OpenGL programming.

## Table of contents
1. [Introduction](#introduction)
2. [Prerequisites](#prerequisites)
    1. [Visual Studio Code Extensions](#visual-studio-code-extensions)
    2. [g++](#g++)
3. [Directory Layout](#directory-layout)
    1. [.vscode](#.vscode)
    2. [builds](#builds)
    3. [dependencies](#dependencies)
    4. [src](#src)
4. [Building](#building)
5. [Running](#running)
    1. [Executable](#executable)
    2. Debug [Mode](#mode)
6. [Library Versions](#library-versions)
7. [Helpful links](#helpful-links)

# Introduction
As you may know by now this project is a setup, you need to have **Visual Studio Code** installed before you can actually run this in the way I have intended it to.

**NOTE:** Visual studio code is not required since you can use the g++ to run the project, all visual studio code does for you is a give an environment in which you can write, run and build your code.

# Prerequisites

## Visual Studio Code Extensions
The following extensions are needed:

1. C/C++ (Microsoft)

## g++
This project compiles using the g++ command, on Windows computers this means that you need to have the **MinGW Instalation Manager** installed, from there you can install the following packages:

1. mingw32-gcc-g++

These can all be accessed from the Basic Setup tab of the installer.

When these packages are installed you need to add the directory where the g++ command is located to your PATH variable.

when all of that is finished you should be able to run the project.

# Directory Layout
The project directory is layed out like this:

* .vscode
* builds
* dependencies
* src
    * shaders

### **.vscode**
this directory houses the visual studio code project setup and options. in here you can **add your own files to the build process (tasks.json)** and **edit your include path (c_cpp_properties.json)**

### **builds**
this directory houses platform specific builds, the current **supported builds** are **Windows and Linux**.

### **dependencies**
This folder contains all of the libraries that your project may use, it loads in and sets up the following libaries:

1. GLFW
2. GLAD
3. GLM

The main layout of this directory is a folder with the name of the dependency in UPPERCASE with the library contents located within that folder.

**Any other dependencies that you may want to add need to be added to the build process** (.vscode/tasks.json)

### **src**
This folder contains all of your source code files ( for example, .cpp and .h files). it also houses your glsl shaders (src/shaders)

The src folder also provides you with 3 .cpp and 2 .h files, these are:

1. main.cpp
2. engine.cpp + engine.h
3. shader.cpp + shader.h

**engine.cpp + engine.h**<br/>
These files are your main files from where you can write your code. It gives you some functions in which you can do some initialization, input, update and render logic.

**shader.cpp + shader.h**<br/>
This file is a basic shader class in which you can load your shaders.<br/>
**Sample Code:**
```cpp
Shader basicShaderProgram;

// Set vertex and fragment shader, then compile it to a program
basicShaderProgram.setVertexShader("src/shaders/basicVertexShader.glsl");
basicShaderProgram.setFragmentShader("src/shaders/basicFragmentShader.glsl");
basicShaderProgram.compile();

// Bind the shader
basicShaderProgram.use();
```
**Note:** This project does not include .glsl shader files into the executable, this is up to the developer and this project does not provide the tools or functionality to do that.

# Building
To build your project you **use the default building hotkey of Visual Studio Code** (CTRL + SHIFT + BUILD), if your build hotkey is different please check within Visual Studio Code which combination it is.

# Running

**Executable**<br/>
To run you project you first need to **build your project** and then execute the .exe file located within your **builds/[PLATFORM]** folder.

**Note:** This project does not include .glsl shader files into the executable, this is up to the developer and this project does not provide the tools or functionality to do that. In order to run the executable successfully you need to create the following folders within your **builds/[PLATFORM]** folder: src/shaders/[YOUR_SRC/SHADERS_FOLDER_CONTENTS]. after that just paste the contents of your shader folder, that is located in the src folder, into the newly created folder structure.

**Debug Mode**<br/>
To run the project in debug mode you **use the default debug hotkey of Visual Studio Code** (CTRL + F5), if your debug hotkey is different please check within Visual Studio Code which combination it is.

# Library Versions
1. GLFW (Version 3.3.bin.win32)
2. GLAD (gl: 4.6, profile: Core, extensions: none)
3. GLM (Version 0.9.9.6)

This whole setup works on the latest version of Visual Studio Code as of 29-12-2019, which is version 1.14.1 (user setup)

# Helpful links
* [MinGW Installation Manager](https://osdn.net/projects/mingw/releases/)
* [g++ compiling](https://www.cs.bu.edu/fac/gkollios/cs113/Usingg++.html)
* [GLFW library](https://osdn.net/projects/mingw/releases/)
* [GLAD library](https://glad.dav1d.de/)
* [GLM library](https://glm.g-truc.net/0.9.9/index.html)