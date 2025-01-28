# Uncontrolled setInterval in useEffect

This repository demonstrates a common mistake in React: using `setInterval` within the `useEffect` hook without proper cleanup. This leads to memory leaks and unexpected behavior.

The `bug.js` file shows the incorrect implementation. The `bugSolution.js` file provides the corrected version with a cleanup function.

## Bug

The `setInterval` function is used to increment a counter every second. However, there's no mechanism to clear the interval when the component unmounts, leading to continued calls to `setInterval` even after the component is no longer needed.

## Solution

The solution involves returning a cleanup function from the `useEffect` hook. This function clears the interval when the component is unmounted, preventing memory leaks.