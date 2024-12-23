# JavaScript Closure Issue with setTimeout

This repository demonstrates a common JavaScript closure issue related to the use of `setTimeout` within a loop.  The problem arises because the closures created by `setTimeout` do not capture the value of `i` at the time of their creation, but rather capture a reference to the variable itself.  As the loop iterates, the value of `i` changes, leading to all closures logging the final value of `i` instead of the value at the time each `setTimeout` was called.

## How to reproduce

1. Clone this repository.
2. Open `bug.js` and run it.
3. Observe that the output is '10' printed 10 times instead of 0 through 9.

## Solution

The solution involves using an immediately invoked function expression (IIFE) or `let` to create a new scope for each iteration, ensuring that each closure captures its own unique value of `i`.

See `bugSolution.js` for the corrected code.