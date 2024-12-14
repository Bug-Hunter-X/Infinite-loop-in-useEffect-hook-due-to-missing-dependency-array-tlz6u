# React useEffect Hook Bug: Infinite Loop

This repository demonstrates a common bug in React applications involving the `useEffect` hook.  The bug arises from omitting the dependency array in `useEffect`, leading to an infinite loop.

## Problem
The provided `MyComponent` uses the `useEffect` hook without specifying a dependency array.  This causes the effect to run after every render, triggering a continuous update cycle that results in an infinite loop and potential browser crashes. The `console.log` statement within the effect will show the continuously updating count value.

## Solution
The solution involves correctly specifying the dependency array.  In this case, we only want the effect to run when `count` changes, so `[count]` is used as the dependency array. The `useEffect` function will only execute when the values in this array change.

## How to Reproduce
1. Clone this repository.
2. Run `npm install` to install the necessary dependencies.
3. Run `npm start` to start the development server.
4. Observe the infinite loop in the browser's console and the rapidly increasing count in the UI (if it renders).

## How to Fix
1. Examine your `useEffect` hooks carefully.
2. Always specify a dependency array unless the effect should run only once after the initial render (use an empty array: `[]`).
3. Ensure that all values used within the `useEffect` are included in the dependency array to prevent unintended re-renders and infinite loops. 