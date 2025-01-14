# Race Condition in DOM Manipulation with setTimeout

This repository demonstrates a subtle race condition that can occur when manipulating the DOM using `setTimeout` in JavaScript. The core issue arises when a function attempts to modify the DOM before the browser has fully rendered the necessary elements.

## Bug Description
The provided `bug.html` file contains two JavaScript functions. The first, `myFunction`, successfully modifies the innerHTML of a div element.  The second, `anotherFunction`, attempts to do the same thing but is scheduled to run using `setTimeout(anotherFunction, 0)`.  Because `setTimeout` is asynchronous and doesn't guarantee immediate execution, there's a chance the element may not exist yet, thus causing an error.

## Solution
The `solution.html` file shows how to resolve this race condition using a more robust approach. It uses a combination of `addEventListener` and a check to make sure the element exists before attempting manipulation.

This example highlights the importance of understanding the asynchronous nature of JavaScript and the timing of DOM updates in browser environments.