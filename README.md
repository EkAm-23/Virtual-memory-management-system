# Virtual Memory Manager

This project simulates a **virtual memory management system** in C++, featuring multiple page table implementations and performance comparisons. It mimics how operating systems allocate memory to multiple processes, perform address translation, and manage page hits/misses.

## Features

- 🧠 **Multiple Page Table Implementations**
  - **Map-based page table** using hash maps
  - **Single-level page table** using arrays
  - **Two-level hierarchical page table**

- ⚙️ **Memory Manager**
  - Manages physical page frames
  - Allocates free pages on demand
  - Tracks used vs. free memory

- 📊 **Performance Comparison**
  - Compares the execution time, page hits, and misses across all three page table implementations
  - Reports total memory allocated and free memory available after simulation

- 🧵 **Multithreaded Test Case Generation**
  - Uses `pthreads` to simulate concurrent memory access from multiple tasks
  - Each thread generates random, page-aligned memory requests for a unique task

- 📄 **Trace File Parsing**
  - Reads trace files in the format: `T<task_id>:<hex_address>:<size>KB`
  - Parses and processes memory requests for multiple simulated tasks

## Project Structure

├── config.hpp # Configuration: page size, memory size, section sizes, etc.\
├── io.hpp / io.cpp # Parses trace files and formats memory sizes\
├── memory_manager.hpp/.cpp # Manages physical memory frame allocation\
├── task.hpp / task.cpp # Implements page table classes (map, single, two-level)\
├── performance.hpp/.cpp # Runs the simulation and measures results\
├── test.cpp # Multithreaded trace generator for test inputs\
├── trace.txt # Sample output from test module (generated)\
└── Makefile

## How It Works

1. `test.cpp` uses `pthreads` to generate a trace file with memory access requests from multiple simulated tasks.
2. `performance.cpp` reads this file, assigns each task its own page table, and simulates memory access.
3. The system records page hits/misses and evaluates performance for each page table type.

## Build and Run

### To compile and run the project:

-Clone the repository to your local machine.\
-Navigate into the project directory:
```
cd "implementation of a memory management system"
```
Build the project using the provided Makefile:
```
make
```
The Makefile handles all the compiling and linking automatically, displaying the performance metrics of the three page table implementations.
