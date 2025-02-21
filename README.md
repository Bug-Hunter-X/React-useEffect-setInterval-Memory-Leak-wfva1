# React useEffect setInterval Memory Leak

This repository demonstrates a common error in React applications: using `setInterval` within the `useEffect` hook without proper cleanup.  This can cause memory leaks and unexpected behavior as the interval continues to run even after the component unmounts.

The `bug.js` file shows the problematic code. The `bugSolution.js` file provides a corrected version that includes a cleanup function to stop the interval when the component is unmounted.

## How to Reproduce

1. Clone this repository.
2. Run `npm install`
3. Run `npm start`
4. Observe the counter incrementing every second.
5. Navigate away from the component.  The counter should stop.  In the buggy version, it will continue in the background.

## Solution

The solution involves adding a return statement to the `useEffect` callback which clears the interval using `clearInterval` before the component unmounts.