# Week 04 – Day 16: Ghidra

## Overview

In this practical task, I installed and explored Ghidra, an open-source reverse-engineering tool. The main purpose of this activity was to understand the basic Ghidra workflow, create a project, import a sample file, run analysis, and explore its important features.

Ghidra is commonly used for malware analysis, software reverse engineering, vulnerability research, binary auditing, disassembly, and decompilation.

## Checking the Java Version

Before installing Ghidra, I checked the installed Java version because Ghidra requires Java 17 or later.

```bash
java -version
```

## Installing Ghidra

I installed Ghidra by running the following command:

```bash
sudo apt install ghidra
```

## Launching Ghidra

After completing the installation, I launched Ghidra using:

```bash
ghidra
```

When Ghidra opened for the first time, I reviewed and accepted the user agreement.

## Creating a New Project

I created a new non-shared project in Ghidra and selected a suitable location for storing the project files.

After creating the project, I opened the CodeBrowser tool from the Ghidra dashboard.

## Creating a Sample C++ File

For the file-import activity, I created a small C++ file named `code.cpp`.

```cpp
#include <iostream>

int main() {
    std::cout << "Hello Ghidra";
    return 0;
}
```

The file was saved and imported into the Ghidra project.

## Importing the File

I used the Import File option inside CodeBrowser to import the `code.cpp` file.

During the import process, I selected the raw binary format and used the following language configuration:

```text
6502:LE:16:default
```

After confirming the import settings, Ghidra displayed the Import Results Summary.

A memory-block warning appeared during the import process, but the file was still imported successfully, so I continued with the practical task.

## Running the Analysis

After importing the file, I opened it in CodeBrowser and allowed Ghidra to run its automatic analysis.

The imported data was displayed inside the Listing window.

Because the C++ source file was imported as raw binary data instead of a compiled executable, the results were different from a normal executable analysis. However, the file was still useful for exploring the main Ghidra features.

## Bytes Viewer

I opened the Bytes window to view the hexadecimal representation of the imported file.

This window displayed the raw bytes stored inside the `code.cpp` file.

## Decompiler

I opened the Decompiler window to explore where Ghidra normally displays reconstructed high-level code.

Since the imported file was a raw C++ source file and not a compiled executable, Ghidra could not generate normal decompiled program code from it.

## Function Graph

I opened the Function Graph window to explore how Ghidra displays the control flow of identified functions.

The selected location was not detected as a valid function because the imported file was raw binary data.

## Script Manager

I opened the Script Manager to view the scripts available in Ghidra.

The Script Manager can be used to automate analysis tasks and extend the functionality of Ghidra.

## Memory Map

I opened the Memory Map to view the memory blocks created during the import process.

This section showed how Ghidra mapped the imported file into memory.

## Register Manager

I opened the Register Manager to explore the processor registers available for the selected 6502 architecture.

## Symbol Table

I opened the Symbol Table to view the symbols available inside the imported program.

Symbols can include labels, functions, variables, addresses, and other program elements.

## Symbol References

I also explored the Symbol References feature.

This feature is used to find the locations where a selected symbol or address is referenced inside a program.

## Ghidra Features Explored

During this practical task, I explored the following features:

- Ghidra Project Manager
- CodeBrowser
- Raw Binary Import
- Automatic Analysis
- Listing Window
- Bytes Viewer
- Decompiler
- Function Graph
- Script Manager
- Memory Map
- Register Manager
- Symbol Table
- Symbol References

## Result

I successfully installed and launched Ghidra, created a new project, imported a sample C++ file, ran the analysis process, and explored the main reverse-engineering features available inside CodeBrowser.

This practical helped me understand the basic workflow of Ghidra and the purpose of important features such as the Bytes Viewer, Decompiler, Function Graph, Script Manager, Memory Map, Register Manager, Symbol Table, and Symbol References

## Task Status

Status: Completed
