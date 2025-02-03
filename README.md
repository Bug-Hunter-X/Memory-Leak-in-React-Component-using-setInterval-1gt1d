# React setInterval Memory Leak

This repository demonstrates a common error in React applications involving the `setInterval` function within the `useEffect` hook, leading to memory leaks.  The example shows how to correctly use `setInterval` by including a cleanup function to prevent the accumulation of timers.

## Problem

The original code snippet uses `setInterval` to update a counter every second. However, it fails to provide a cleanup function within the `useEffect` hook. This means that every time the component renders (even if it is unmounted), a new `setInterval` is created, resulting in multiple timers running and consuming memory.

## Solution

The corrected code includes a cleanup function that uses `clearInterval` to stop the timer when the component unmounts or when the dependencies of `useEffect` change. This ensures that no unnecessary timers are left running and prevents the memory leak.