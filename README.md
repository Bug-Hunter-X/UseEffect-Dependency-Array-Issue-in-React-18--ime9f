# React 18 useEffect Hook and Automatic Batching Bug

This repository demonstrates a common issue encountered when using the `useEffect` hook in React 18 and later versions. The automatic batching introduced in React 18 can cause unexpected behavior if the dependencies array of `useEffect` is not properly managed.

## Bug Description

The bug arises from incorrect dependency management within the `useEffect` hook. When a state variable is updated within an event handler, React 18 automatically batches updates. If the state variable is not included in the `useEffect`'s dependency array, the effect will not immediately reflect the state change. It will run only on the subsequent render cycle.

## Solution

The solution is to ensure that the state variable which is changed within an event handler is included in the dependency array of the `useEffect` hook. This ensures that the effect runs whenever the variable changes. See `bugSolution.js` for the corrected code.