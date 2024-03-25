# XV6 Page Table Visualization Tool

This README provides details about the XV6 Page Table Visualization tool, a feature implemented to enhance the understanding and debugging of page tables in the XV6 operating system.

## Objective

The primary goal of this project is to develop a function that prints the contents of the page tables in the XV6 operating system. This visualization aids in comprehending the structure and behavior of page tables.

## Key Features

- **Function Implementation**: The tool includes a function `ptprint(pde_t *pgdir)` that takes a page directory entry as an argument and prints the page table tree.
- **Integration with XV6**: The function is seamlessly integrated into the XV6 operating system and is executed during the process lifecycle.
- **Page Table Display**: It displays entries of the page directory and page tables, including PTEs that refer to deeper levels in the page-table hierarchy.
- **Depth Indication**: The display format includes indentation to indicate the depth of each entry in the page table tree.
- **Selective Printing**: The tool is designed to print only valid PDEs/PTEs with user privileges.
- **Enhanced Understanding**: It serves as a valuable tool for understanding the mapping and structure of page tables in XV6.

## Installation

1. **Download XV6 Source Code**: 
   - Retrieve the source code from `/cs5348-xv6/src/xv6.tar.gz`.
   - Extract the source code using `tar -zxvf xv6.tar.gz`.

2. **Project Integration**:
   - **Implement `ptprint` Function**: Code the `ptprint()` function within `vm.c`.
   - **Declare Function Prototype**: Add the prototype for `ptprint()` in `defs.h`, ensuring proper placement within the file.
   - **Code Insertion in `exec.c`**: Incorporate the provided code snippet before `return 0` in `exec.c`.

## Usage

- **First Process Visualization**: By default, the tool will print the page tables of the first process at the point where XV6 has finished executing `init`.
- **General Usage**: For broader usage, remove the specific condition in `exec.c` and call `ptprint` unconditionally to observe the page tables for different processes and scenarios.
