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

- `` `launch.json` ``: The "launch.json" file contains the launch configuration for debugging in C/C++ projects. For more information on how to configure this file, check out the [official documentation](https://code.visualstudio.com/docs/editor/debugging#_debugger-extensions "Debugging").
    
    Note that Bash is not a usable external terminal for debugging. If you are unable to debug your code, it is likely due to this limitation. To use an external terminal for debugging, you will need to install a terminal emulator such as gnome-terminal and set it as the default. Alternatively, you can use the integrated terminal by changing the value of the 'externalConsole' variable to false.

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