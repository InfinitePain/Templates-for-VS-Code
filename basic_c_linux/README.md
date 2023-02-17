# Basic C Linux Configuration

This folder is preconfigured to help users get started with C programming on Linux. It includes the following files and folders:

- `` `.vscode` `` folder: Contains configurations for Visual Studio Code
- `` `bin` `` folder: Contains the compiled executable files
- `` `main.c` `` file: The main C source code file

## .vscode Folder

The .vscode folder includes the following files:

- `` `c_cpp_properties.json` ``:  This file sets the path for the compiler and any libraries used in the project. By default, it is set to use the system GCC compiler ( `` `/usr/bin/gcc` ``) and assumes that all necessary libraries are in their default folders. If the user has a different configuration or library location, they should modify this file accordingly. To add include paths, modify the "includePath" setting in this file. For example:

    ```json
    "includePath": [
        "${workspaceFolder}/**",
        "/path/to/include"
    ]
    ```


    In this example, the includePath setting includes all directories under the workspace folder and the system header files located in the `` `/path/to/include` `` directory. Note that the `` `${workspaceFolder}/**` `` syntax recursively includes all directories under the workspace folder, which can be convenient but may also include unwanted directories. If you want to include only specific directories under the workspace folder, you can use the absolute path of those directories instead. For further information, see the [official documentation](https://code.visualstudio.com/docs/cpp/c-cpp-properties-schema-reference "c_cpp_properties.json reference").

- `` `tasks.json` ``: This file contains tasks that can be executed within Visual Studio Code. There is one task defined for Linux, and it builds the project using the GCC compiler. To set a task as the default build task, you can add the following configuration to the task you want to use as the default in the tasks.json file:

    ```json
    "group": {
        "kind": "build",
        "isDefault": true
    }
    ```
    This will set the build task as the default task to run when the user executes the "Run Build Task" command or presses F7. If the user needs to include any libraries, they should add the proper flags to the `` `tasks.json` `` file. For more information on tasks and how to integrate with external tools, see the comments in the `` `tasks.json` `` file and refer to the [official documentation](https://code.visualstudio.com/docs/editor/tasks "Integrate with External Tools via Tasks").

- `` `launch.json` ``: This file sets the launch configuration for debugging. It contains three configurations: "Run on Terminator", "Debug C/C++ on Linux (Integrated Terminal)", and "Debug with gdb on Terminator".

    - `Run on Terminator`: This configuration runs the compiled executable using the Terminator terminal emulator. It sets the current working directory to the workspace folder and passes the name of the executable to Terminator to run.
    - `Debug C/C++ on Linux (Integrated Terminal)`: This configuration launches the GDB debugger in the integrated terminal and sets up debugging for a C or C++ program. It sets the current working directory to the workspace folder and passes the name of the executable to GDB to debug. This configuration supports breakpoints, stepping through code, and examining variables.
    - `Debug with gdb on Terminator`: This configuration runs the GDB debugger in the Terminator terminal emulator. It sets the current working directory to the workspace folder and passes the name of the executable to GDB to debug. This configuration is similar to the "Debug C/C++ on Linux (Integrated Terminal)" configuration, but it uses the Terminator terminal emulator instead of the integrated terminal.

     Note that the second configuration ("Debug C/C++ on Linux (Integrated Terminal)") is more feature-rich and provides more debugging capabilities than the third configuration ("Debug with gdb on Terminator"). If you are using a native Linux machine, you can modify the appropriate setting in the configuration to debug from an external terminal. This is set to use the integrated terminal by default to ensure compatibility across different environments, and to avoid potential issues with debugging in WSL. To do this, modify the value of the "externalConsole" field in the configuration to true. For more information about the launch.json file and how to configure it, see the [official documentation](https://code.visualstudio.com/docs/editor/debugging#_debugger-extensions "Debugging").

## bin Folder

The `` `bin` `` folder contains the compiled executable files. These are automatically created when the user runs the build task in Visual Studio Code.

## main.c File

The `` `main.c` `` file is the main source code file for the project. The user can add additional files as needed, but should ensure that they are included in the build tasks in `` `tasks.json` ``.

It is important to note that this configuration is preconfigured to use the system GCC compiler. If the user wishes to use a different compiler, they must modify the necessary configurations in `` `tasks.json` `` and `` `c_cpp_properties.json` `` accordingly.

If the user needs to include any libraries, they should add the proper flags to the `` `tasks.json` `` file and the path to `` `c_cpp_properties.json` `` file. For further information, see the comments in the `` `tasks.json` `` file.

## Extensions

We recommend installing the following extensions for Visual Studio Code:

- C/C++ Extension Pack
- IntelliCode
- IntelliCode API Usage Examples
- IntelliCode Completions

These extensions will help improve the C programming experience within Visual Studio Code.