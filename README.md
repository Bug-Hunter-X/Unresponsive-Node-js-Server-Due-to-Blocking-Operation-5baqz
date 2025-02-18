# Unresponsive Node.js Server

This repository demonstrates a common issue in Node.js where a long-running operation in a request handler blocks the event loop, making the server unresponsive.  The `server.js` file contains the problematic code, while `serverSolution.js` shows how to fix it using asynchronous operations.

## Problem

The `server.js` file creates a simple HTTP server. However, the request handler contains a `while` loop that keeps the CPU busy for 5 seconds.  During this time, the server cannot handle any other requests, leading to unresponsiveness.

## Solution

The `serverSolution.js` file demonstrates a solution using asynchronous operations.  Instead of blocking the event loop, the solution uses `setTimeout` to schedule the response after 5 seconds, allowing the server to continue processing other requests during the delay.