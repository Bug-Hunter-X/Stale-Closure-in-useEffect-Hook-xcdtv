# Stale Closure in React's useEffect Hook

This repository demonstrates a common error in React applications involving stale closures within the useEffect hook.  The example showcases how referencing state variables directly within the callback function of setInterval can lead to unexpected behavior.

## Problem
The provided code attempts to increment a counter every second using setInterval. However, due to the way closures work in JavaScript, the `count` variable inside the setInterval callback is not updated with the latest value from the state.  This results in the counter not incrementing correctly.

## Solution
The solution utilizes the functional update pattern for useState. Instead of directly accessing the `count` variable, the setter function (`setCount`) is called with a function that takes the current state and returns the new state. This ensures that the latest value of `count` is always used.