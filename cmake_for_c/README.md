# CMake for C

This folder is preconfigured for the CMake projects and allows you to start building C projects with ease. It comes with some pre-defined settings, and it assumes that everything you need for your project is located in default folders. If your compiler is MinGW64 or similar, everything should work out of the box. However, if you have installed your compiler in a different folder, you will need to adjust the corresponding configurations.

## Getting started

To get started with CMake for C, follow these simple steps:

- Install CMake on your system. You can download it from the [official website](https://cmake.org/download/ "CMake Download")
- Open the project in Visual Studio Code.
- Press F7 or run the CMake: Build command from the command palette.
- Select a build configuration from the dropdown menu in the bottom left corner of the window.
- Press F5 to start debugging.

## Launch configurations

The template comes with a preconfigured launch.json file that allows you to debug your project with ease. The launch.json file defines two launch configurations: gdb Debug and MSVC Debug.

## CMakePresets.json

CMake for C also includes a preconfigured CMakePresets.json file that provides several build and configure presets. These presets include:

### Windows Presets:

- x64 Debug MSVC Ninja
- x64 Release MSVC Ninja
- x64 Debug MSVC Visual Studio 17
- x64 Release MSVC Visual Studio 17
- x64 Debug GCC Ninja
- x64 Release GCC Ninja
- x64 Debug Mingw64-GCC VS17
- x64 Release Mingw64-GCC VS17

### Linux Presets:

- x64 Debug GCC Ninja
- x64 Release GCC Ninja

Each preset specifies a compiler and a generator, and includes two build options: clean build and build.

## Configuring the project

To configure the project, modify the CMakeLists.txt file. The file is already set up to include the include directory and to compile all source files in the src directory. The install command is also set up to install the binary file and the CMakeProjectConfig.h file.

## CMakeProjectConfig.h.in

The `` `CMakeProjectConfig.h.in` `` file is a configuration file that is used to pass some of the CMake settings to the source code. The file defines the `` `PROJECT_VERSION_MAJOR` ``, `` `PROJECT_VERSION_MINOR` ``, and `` `PROJECT_VERSION_PATCH` `` macros. These macros are replaced by their corresponding values at configuration time.

For more information on CMake, check out the [official documentation](https://cmake.org/documentation/ "CMake Documentation").