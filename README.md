# React useEffect Hook Memory Leak

This repository demonstrates a common error in React's `useEffect` hook: forgetting to include a return statement for cleanup. This can lead to memory leaks if the component unmounts before cleanup actions are complete.  The solution shows how to properly implement the return statement to prevent this issue.

## Bug Description

The `useEffect` hook, without a return statement, will not properly clean up when the component unmounts. This can cause resources to be left behind, leading to memory leaks.

## How to reproduce

1. Clone this repository.
2. Run `npm install`
3. Run `npm start`
4. Observe the console logs. Repeated mounting and unmounting will show the absence of cleanup messages.

## Solution

The solution includes a return function in the `useEffect` hook that performs cleanup operations, such as canceling timers or detaching event listeners.  This ensures resources are released when the component is unmounted.