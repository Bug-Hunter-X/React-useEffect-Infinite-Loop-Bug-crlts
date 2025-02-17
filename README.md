# React useEffect Infinite Loop Bug

This repository demonstrates a common but easily overlooked bug in React applications involving the `useEffect` hook. The bug causes an infinite loop due to improper state updates within the `useEffect` dependency array.

## Bug Description

The `bug.js` file contains a React component that attempts to increment a state variable (`count`) within the `useEffect` hook's callback. The dependency array is empty (`[]`), implying the effect should run only once after the initial render. However, the state update within the effect triggers another render, leading to an infinite loop.

## Solution

The `bugSolution.js` file demonstrates how to fix the bug. Instead of directly updating the state in the effect, we use a different approach that avoids triggering re-renders infinitely. The solution uses the `useRef` hook to track the previous state, making sure the updates will not lead to an infinite loop.