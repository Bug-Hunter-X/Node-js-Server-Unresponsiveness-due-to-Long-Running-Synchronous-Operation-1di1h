# Node.js Server Unresponsiveness

This repository demonstrates a common Node.js issue where a long-running synchronous operation in the request handler blocks the event loop, causing the server to become unresponsive.  The `server.js` file shows the buggy code, and `serverSolution.js` provides a corrected version utilizing asynchronous operations.

## Problem

The original code includes a `while` loop that simulates a 5-second task. This blocks the event loop, preventing the server from handling subsequent requests.  All incoming requests during the 5 seconds will be queued and remain unprocessed, effectively making the server unresponsive.

## Solution

The solution demonstrates how to handle long-running tasks asynchronously.  This allows Node.js to continue processing other events while the long task completes.  Asynchronous operations prevent the event loop from being blocked, avoiding the unresponsiveness issue.