# React setInterval Memory Leak

This repository demonstrates a common mistake when using `setInterval` within a React component's `useEffect` hook.  Failing to properly clean up the interval leads to memory leaks, especially if the component unmounts before the interval is cleared.

The `bug.js` file shows the problematic code. The `bugSolution.js` file provides the corrected implementation.

## How to reproduce

1. Clone this repository.
2. Navigate to the directory.
3. Run `npm install` to install dependencies.
4. Run `npm start` to start the development server.
5. Observe the behavior of the counter in the browser.
6. Unmount the component (e.g., navigate away from the page), then open the developer console and check for warnings or errors related to memory leaks (depending on the browser's warning system).

## Solution

The solution involves using the return value of `useEffect` to define a cleanup function. This cleanup function clears the interval when the component unmounts, preventing the memory leak.

## Additional Notes

This is a simplified example. In a more complex application, memory leaks caused by improperly handled intervals can be more challenging to track down.