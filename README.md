# React Memory Leak: setInterval without Cleanup in useEffect

This repository demonstrates a common React bug: a memory leak caused by improper usage of `setInterval` within the `useEffect` hook.  The provided code lacks a cleanup function to clear the interval, leading to continuously running timers even after the component unmounts. This results in memory leaks and potential performance issues.

## Bug Description:
The `MyComponent` uses `setInterval` to update a counter every second. However, it fails to include a cleanup function in the `useEffect` hook's return statement.  This means the interval continues running even after the component is unmounted, resulting in a memory leak.

## Solution:
The solution involves adding a cleanup function within the `useEffect` hook's return statement to clear the interval using `clearInterval` before the component unmounts. This ensures that the interval is stopped, preventing memory leaks and ensuring the application runs smoothly.
