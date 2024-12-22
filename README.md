# React 19 StrictMode Bug: Unexpected Console Output During Render

This repository demonstrates a common error encountered when using React 19's StrictMode.  The bug arises from unintended side effects within the useEffect hook, specifically console logging during the render phase.

## Bug Description

In React 18 and earlier, StrictMode didn't always strictly enforce the rules of render phase.  React 19 and beyond is more strict about what should happen in the render phase.  The `useEffect` hook in the example code logs a message to the console each time the component renders. This is generally undesirable and can lead to unexpected behavior or errors, particularly in StrictMode.  StrictMode is designed to highlight potential issues with the application, so it will report this as an error.

## Solution

The solution is to ensure that the `useEffect` hook only runs when the component's state has changed. The changes in the solution code prevent the console log from being run during the initial render and instead allows it only when the count state is updated.