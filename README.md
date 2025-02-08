# Closure Problem in `setTimeout` Loop
This repository demonstrates a common JavaScript closure issue encountered when using `setTimeout` within a loop. The problem arises because the `setTimeout` callback function does not capture the value of the loop variable (`i`) at the time of its creation, but rather captures a reference to the variable itself. This means that by the time the `setTimeout` callbacks finally execute, the value of `i` has already changed.

## How to reproduce
1. Clone this repository.
2. Run `bug.js`.
3. Observe that instead of logging numbers 0-9 with a delay, it logs 10 ten times.

## Solution
The solution involves using an immediately invoked function expression (IIFE) to create a new scope for the `i` variable at each iteration of the loop. This ensures that each `setTimeout` callback captures a unique copy of the variable's value.