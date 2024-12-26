# Node.js Unhandled Exception Bug

This repository demonstrates a common yet often overlooked bug in Node.js HTTP servers: unhandled exceptions within the request listener.  If an error occurs within the requestListener function and is not properly caught, the server may fail silently, continue running in an unresponsive state, and not provide helpful error messages.

## Bug Description

The provided `bug.js` demonstrates a simple HTTP server. However, it lacks proper error handling within the `requestListener`.  If an exception occurs during request processing, the server will not terminate or log a meaningful error message, leading to an unresponsive server.

## Solution

The `bugSolution.js` file shows the corrected code. It includes a `try...catch` block within the `requestListener` to handle potential exceptions gracefully.  This ensures that any errors are logged to the console, and the server responds appropriately (e.g., with an error status code) rather than silently failing.

## How to Reproduce

1.  Clone the repository.
2.  Run `bug.js` using `node bug.js`.
3.  Attempt to trigger an error (e.g., by introducing a deliberate error in the `requestListener`). Observe the lack of clear error messages.
4.  Run `bugSolution.js` using `node bugSolution.js`. Observe the improved error handling and logging.