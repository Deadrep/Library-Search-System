# Library-Search-System

## Table of Contents
1. [Introduction](#introduction)
2. [Getting Started](#getting-started)
3. [Application Demonstration](#application-demonstration)
4. [Data Structure Selection and Analysis](#data-structure-selection-and-analysis)
5. [Testing Approach](#testing-approach)
6. [Limitations](#limitations)
7. [Recommendations for future](#Recommendations-for-future)

### Introduction
This repository contains the design and implementation of a C++ based library search system that allows users to search, add and remove books efficiently using appropriate data structures and algorithms. It is suitable for use in libraries with a large collection of books, and useful for anyone looking to implement a library search system or improve their understanding of data structures and algorithms.

### Getting Started

#### Prerequisites
- A C++ compiler (such as GCC or Clang)
- A text editor (such as Visual Studio Code)
- MinGW (Minimalist GNU for Windows) or enable the Windows Subsystem for Linux (WSL) and install a Linux distribution of your choice to enable the use of make files.
- GNU Make

OR

- An alternative method for compiling and running the program is using [repl.it](https://repl.it/), which is a collaborative online IDE.

#### Instructions for Running the Program
1. Clone the repository or download the files.
2. Run the following command in your terminal or command prompt:
```bash
make
```

#### Getting rid of object and executables
Before running the `make` command again after making updates to the program's source code, use the following command to clean object files and executables:
```bash
make clean
```
> **Note**
> : Make sure that you have enabled the use of make files before running the above commands.

### Application Demonstration
| ![](https://github.com/Deadrep/Library-Search-System/blob/main/SC_1.png) | ![](https://github.com/Deadrep/Library-Search-System/blob/main/SC_2.png) | ![](https://github.com/Deadrep/Library-Search-System/blob/main/SC_3.png) |
| --- | ----------- | ----------- |
| *Screenshot 1: Search functionality demonstration* | *Screenshot 2: Add functionality demonstration* | *Screenshot 3: Remove functionality demonstration* |

### Data Structure Selection and Analysis

#### Hash Tables

The library system implemented in this project contains a large number of books, which are arranged based on title, author, ISBN, and quantity. To improve the efficiency of the system, the data structure chosen was Hash Tables (using Separate chaining). This data structure assigns a unique key to each book in the library system, allowing for quick retrieval of the book's location.

#### Separate Chaining (Open Hashing)

The Hash Table is implemented using the Separate Chaining method, where entries in the table are linked lists. If two elements have the same hash output or code, they are entered into the same linked list. This method is effective in looking up a particular key in a uniformly distributed table, and is efficient in deletion. However, if all keys have the same hash code, the cost of lookup is proportional to the number of keys in the table.

#### Comparison with Binary Search Tree (BST)

In comparison to a BST implementation, the code is simpler and search times are optimal (constant). The use of an efficient hash function can also satisfy the uniform hashing assumption. Hashing can be faster than a Red-Black BST, depending on the type of key. For typical key types, hashing will be significantly faster because it uses only a constant number of operations.

### Testing Approach

#### Unit Testing
The testing process for this project involves testing individual program elements separately, such as individual functions or methods inside an object. The unit testing was automated, and the catch2 test automation framework was used to write and run the program tests. The setup part consists of initializing the system with the test case inputs and expected outputs, and the objects or methods to be tested are called. Finally, the assertion part compares the result of the input to the expected results. If the assert value is true, there are no errors.

#### Test Cases

| Test_coreFun | Test_fileActions | Test_hashtableDeleted |
| --- | ----------- | ----------- |
| This test verifies the functionality of adding, removing, and searching books within the library system. | This test verifies the functionality of reading, adding, and removing books from the books.txt file within the library system. | This test verifies that the hash table and its contents are properly deleted when the program is closed. |

##### Instructions for Running the test program
Run the following commands in your terminal or command prompt:
```bash
g++ -o <Assign-a-name-of-your-choice-to-the-compiled-program> testCase.cpp
./<Assign-a-name-of-your-choice-to-the-compiled-program>
```

> **Note**

> - Do not include the greater-than or less-than signs when specifying the desired program name.

> - Ensure that the catch.hpp file is present in the designated folder.

### Limitations
- The user must enter the complete book name for a successful search, which can be inconvenient. 
- The book details cannot be modified or changed. 
- The title must be entered exactly when searching or removing a book.

### Recommendations for future
- Improve the user experience by implementing a GUI based system and incorporating databases for easier retrieval and storage, as well as increased security.
- Implement barcode scanning for book identification.
- Improve unit testing methods for increased findability, accessibility, reusability, and interoperability.
