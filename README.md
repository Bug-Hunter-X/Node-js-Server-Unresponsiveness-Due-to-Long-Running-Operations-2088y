# Node.js Server Unresponsiveness

This repository demonstrates a common issue in Node.js where long-running operations can block the event loop, making the server unresponsive to new requests.  The `server.js` file contains the buggy code, while `serverSolution.js` provides a solution using asynchronous operations to prevent blocking.

## How to Reproduce
1. Clone this repository.
2. Run `node server.js`.
3. Open a browser and make a request to `http://localhost:3000`.  The request will take 5 seconds to respond.
4. Try to make another request while the first one is still being processed. You will see that the server is unresponsive.

## Solution
The solution uses asynchronous operations (e.g., `setTimeout`) to prevent blocking the event loop. This allows the server to handle other requests concurrently.