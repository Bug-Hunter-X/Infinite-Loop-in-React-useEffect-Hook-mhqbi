# React useEffect Infinite Loop Bug

This repository demonstrates a common bug in React applications involving the `useEffect` hook.  The bug causes an infinite loop because the effect is triggered unnecessarily on every render.

## Bug Description

The provided code uses `useEffect` to log the current count to the console. However, because the dependency array `[]` is empty or missing,  the effect runs after every render, causing `setCount` to be called, which re-renders the component and re-triggers the effect. This creates an infinite render loop.

## How to Reproduce

1. Clone this repository.
2. Run `npm install` to install dependencies.
3. Run `npm start` to start the development server.
4. Observe the infinite logging in the browser's console.

## Solution

The solution involves correctly specifying the dependencies in the dependency array of `useEffect`. By only re-running the effect when the `count` changes, the infinite loop is resolved.
