# Rust Raw Pointer Vector Modification Bug

This repository demonstrates a common error in Rust when using raw pointers with vectors.  Modifying a vector's contents via a raw pointer after the vector has potentially reallocated can lead to undefined behavior.  The example code shows how this can occur and provides a corrected solution.

## Bug Description

The `bug.rs` file contains code that attempts to modify the first element of a vector using a raw pointer obtained via `as_mut_ptr()`.  However, if the vector reallocates (e.g., due to exceeding capacity), this pointer becomes invalid, resulting in unexpected behavior (or a crash).

## Solution

The `bugSolution.rs` file shows a safer approach, avoiding the use of raw pointers when possible and employing techniques like indexing to ensure memory safety. 