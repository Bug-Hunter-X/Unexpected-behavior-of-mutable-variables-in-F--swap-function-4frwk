# F# Mutable Variable Swap Bug

This repository demonstrates a common pitfall when working with mutable variables in F#.  The `swap` function, while seemingly simple, doesn't work as expected because F# passes mutable variables by reference.  This means that modifying `x` and `y` within the function directly alters the original variables.

## Bug

The provided `bug.fs` file contains code that attempts to swap two mutable integer variables. The expected output is 20 10, but the actual output is 20 20 due to the variables being modified in place.

## Solution

The `bugSolution.fs` file offers a corrected version.  It avoids unintended side effects by creating copies of the input variables before swapping their values. This ensures that the original variables remain unchanged outside the scope of the function.