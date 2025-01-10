# F# Mutable Variable Swap Bug

This repository demonstrates a common error in F# when working with mutable variables and attempting to swap their values. The `swap` function, as initially implemented, does not correctly swap the values of `x` and `y`.  The issue lies in the misunderstanding of how mutable variables are passed and modified within functions in F#.

## Problem
The provided code intends to swap the values of two mutable variables using a helper function. However, the values remain unchanged after calling the `swap` function. This is because F# uses call-by-value semantics, so even though the variables are mutable, the function receives copies of their values, not references to them.

## Solution
The solution involves passing the mutable variables by reference using `byref`. This ensures that the function directly modifies the original variables rather than copies.