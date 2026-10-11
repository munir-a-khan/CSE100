# CSE 100 · Algorithm Design and Analysis

UC Merced coursework · Fall 2023 · C++

An archive of sorting, dynamic programming, hashing, greedy, and graph algorithm exercises. Each lab keeps its original source, Makefile, input fixtures, expected outputs, and grading script. The repository contains 12 lab folders; Lab 04 is split into two parts.

## Lab guide

Open a lab folder for its fixtures and build files, or jump directly to the implementation.

| Lab | Implementation | Scope |
| --- | --- | --- |
| [01](Lab01/) | [Source](Lab01/mkhan82.cpp) | Insertion sort; prints the growing sorted prefix |
| [02](Lab02/) | [Source](Lab02/mkhan82.cpp) | Merge sort |
| [03](Lab03/) | [Source](Lab03/mkhan82.cpp) | Divide-and-conquer maximum subarray sum |
| [04-1](Lab04-1/) | [Source](Lab04-1/mkhan82.cpp) | Heap sort |
| [04-2](Lab04-2/) | [Source](Lab04-2/mkhan82.cpp) | Randomized quicksort |
| [05](Lab05/) | [Source](Lab05/mkhan82.cpp) | Radix sort of ten-element vectors, using counting sort |
| [06](Lab06/) | [Source](Lab06/mkhan82.cpp) | Chained hash table with insert, delete, search, and print commands |
| [07](Lab07/) | [Source](Lab07/mkhan82.cpp) | Rod cutting: maximum revenue and cut reconstruction |
| [08](Lab08/) | [Source](Lab08/mkhan82.cpp) | Matrix-chain multiplication cost and parenthesization |
| [09](Lab09/) | [Source](Lab09/mkhan82.cpp) | Huffman codes for six fixed symbols, A–F |
| [10](Lab10/) | [Source](Lab10/mkhan82.cpp) | DFS and graph transposition exercise; incomplete output |
| [11](Lab11/) | [Source](Lab11/mkhan82.cpp) | Prim-style minimum spanning tree parent output |

## Build and inspect a lab

Prerequisites: GNU `g++` with C++11 support. GNU Make is optional; Bash and standard Unix utilities are needed for the original `Grade` scripts. Some sources use variable-length arrays, a GCC extension. Use a compatible GNU environment for those labs.

From the repository root, this example follows the [Lab 01 Makefile](Lab01/Makefile):

```sh
cd Lab01
g++ -std=c++11 -o a.exe mkhan82.cpp
./a.exe < testfiles/t1
```

Alternatively, `make` inside a lab compiles the same source to `a.exe`. Build each lab separately; there is no root build target. Rebuild from source instead of relying on the committed binaries.

The bundled [Lab 01 input](Lab01/testfiles/t1) contains six values, `5 3 2 1 6 4`. Its [expected output](Lab01/testfiles/o1) shows the sorted prefix after each insertion:

```text
3;5;
2;3;5;
1;2;3;5;
1;2;3;5;6;
1;2;3;4;5;6;
```

Each lab has five `testfiles/t*` inputs and `testfiles/o*` reference outputs. After building, `bash Grade` runs the original checks. It rewrites `result` and creates temporary files in the lab directory. Lab 07 also compiles and uses [verifier.cpp](Lab07/verifier.cpp) to check cut solutions. Run these scripts in a disposable working copy if you want to retain the archived result files.

## Archive notes

- Build commands were checked against the Makefiles and source. They were not executed during this documentation update because a C++ compiler was unavailable in the verification environment. The example above is transcribed from the bundled fixtures.
- These are original assignment implementations, with input formats specific to each lab. They do not validate arbitrary input. Lab 05 uses counting buckets for values 0–4; Lab 09 reads six frequencies rather than a text message.
- Lab 10 computes DFS orders but does not print component IDs; its ordering helper indexes an array at `-1` before assigning a valid index. Treat it as an unfinished exercise.
- Lab 06 tests an uninitialized command variable before its first read. Lab 09's equal-frequency comparator returns true for ties. These source limitations are retained in this documentation-only update.
- Existing source comments include external references and textbook attribution. Those references and the original files are preserved.

## Related coursework

[Data Structures](https://github.com/munir-a-khan/Data-Structures-UC-MERCED) · [Computer Organization](https://github.com/munir-a-khan/CSE-31) · [Object Oriented Programming](https://github.com/munir-a-khan/CSE-165) · [Computer Vision](https://github.com/munir-a-khan/CSE-185)
