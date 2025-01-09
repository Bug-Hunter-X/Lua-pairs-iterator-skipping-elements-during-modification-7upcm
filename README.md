# Lua pairs iterator skipping elements during modification

This repository demonstrates a subtle bug in Lua involving the `pairs` iterator and table modification during iteration.  The bug arises when a table is recursively traversed and modified within the loop.

## The Bug

The `bug.lua` file contains a function that recursively iterates over a nested table.  Under certain conditions, if the table structure is changed during iteration, the `pairs` iterator may skip elements, leading to unexpected behavior.

## The Solution

The `bugSolution.lua` file provides a corrected version.  The solution avoids modifying the table while iterating using a copy of the table for processing.

## How to reproduce
1. Clone the repository
2. Navigate to the repository's root directory
3. Run `lua bug.lua` and observe the incorrect output
4. Run `lua bugSolution.lua` and observe the corrected output