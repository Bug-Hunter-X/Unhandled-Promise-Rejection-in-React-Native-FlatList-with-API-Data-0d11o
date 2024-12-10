# Unhandled Promise Rejection in React Native FlatList

This repository demonstrates a bug where an unhandled promise rejection occurs in a React Native FlatList when fetching data from a remote API. The application crashes silently on some Android devices without displaying an error message in the UI. This is an intermittent issue.

## Problem
The `DataList` component uses `useEffect` and `fetch` to retrieve data from a JSONPlaceholder API. While the `try...catch` block handles network errors, unhandled promise rejections can still occur, leading to silent crashes in production builds.

## Solution
The solution involves using a `Promise.resolve().then` to handle the asynchronous operation inside the useEffect hook, ensuring any errors are properly caught and displayed in the UI.