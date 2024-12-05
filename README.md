# React setInterval State Update Bug

This repository demonstrates a common error when using `setInterval` within a React component to update state.  The issue stems from using the stale closure of the count variable within the `setInterval` callback. 

The `bug.js` file shows the incorrect implementation, while `bugSolution.js` provides a corrected version.

## Problem
The initial implementation attempts to increment the counter every second using `setInterval`. However, the `setCount(count + 1)` call uses the initial value of `count` from the closure, leading to the counter always being 1 instead of incrementing correctly. 

## Solution
The solution involves using a functional update to ensure the `setCount` function uses the most recent state value. This is done by using a functional update within the callback of the `setInterval`. This ensures that the counter is correctly updated each second. 