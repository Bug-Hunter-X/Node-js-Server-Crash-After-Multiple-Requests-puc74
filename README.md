# Node.js Server Crash Bug

This repository demonstrates a bug where a Node.js HTTP server crashes after handling a certain number of requests. The server uses the built-in `http` module and appears to be resource-exhausted.

## Bug Description

A simple Node.js HTTP server unexpectedly crashes after handling a number of requests. The cause is not immediately apparent in the code itself.

## Reproduction Steps
1. Clone this repository.
2. Run `node bug.js`.
3. Send multiple requests to the server (e.g., using `curl` or a browser).
4. Observe the server crashing after a certain number of requests.

## Solution
The solution involves using the `cluster` module to create a cluster of worker processes that share the load. This prevents a single process from becoming overwhelmed and crashing.  See `bugSolution.js` for the corrected code.

## Further investigation:
This could also be related to memory leaks, unhandled exceptions, or issues outside of the immediate code snippet.  In a real-world scenario, additional debugging and profiling would be recommended to find the root cause.