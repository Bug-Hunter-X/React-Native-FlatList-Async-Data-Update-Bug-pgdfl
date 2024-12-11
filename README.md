# React Native FlatList Async Data Update Bug

This repository demonstrates a common issue in React Native applications involving asynchronous data fetching and updating FlatLists.  The core problem is that asynchronous operations may complete after the component has unmounted, leading to warnings or crashes.  This example illustrates the problem and provides a solution.

## Problem

The `bug.js` file contains a FlatList that fetches data asynchronously using `useEffect` and `fetch`.  If the component unmounts before the data fetch completes, attempting to update the state causes a warning about setting state on an unmounted component. This example highlights the problem while providing the solution in the `bugSolution.js` file.

## Solution

The `bugSolution.js` file demonstrates how to use `useEffect` cleanup function to prevent the problem.  This effectively avoids updating state after the component is unmounted.  The solution involves checking if the component is still mounted in the `setData` function before updating the state. This ensures that state updates happen only when necessary.