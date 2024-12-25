# React useEffect setInterval Memory Leak

This repository demonstrates a common React bug involving memory leaks caused by the improper use of `setInterval` within the `useEffect` hook.  The example shows a component that increments a counter every second. However, the `setInterval` is never cleared, leading to a memory leak as the component continues to update even when unmounted.

The `bug.js` file contains the buggy code, while `bugSolution.js` provides the corrected version.

## How to reproduce

1. Clone this repository.
2. Run `npm install` to install dependencies.
3. Run `npm start` to start the development server.
4. Observe the counter incrementing. Unmount the component (refresh the page or navigate away) and inspect the console for potential warnings or errors in the browser's developer tools.  The count will continue incrementing even if it is unmounted.

## Solution

The solution involves using the return value of `useEffect` to clear the interval when the component unmounts.