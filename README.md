# Node.js Server Hangs on Long-Running Tasks

This repository demonstrates a common issue in Node.js where long-running operations in request handlers can block the event loop, causing the server to become unresponsive.  The `server.js` file showcases the problem, while `serverSolution.js` provides a solution using asynchronous operations and worker threads.

## Problem

The original `server.js` contains a `while` loop that simulates a long-running task (5 seconds).  During this time, the server is unable to process other requests, leading to hangs and poor performance.  This is because Node.js is single-threaded and the event loop is blocked.

## Solution

The `serverSolution.js` file addresses this by using asynchronous operations to handle long-running tasks.  Worker threads are used to offload the computationally intensive task to a separate thread, preventing it from blocking the event loop.

This example highlights the importance of proper asynchronous programming techniques when dealing with potentially time-consuming operations in Node.js servers to maintain responsiveness and scalability.