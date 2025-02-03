# Express.js Middleware Order Bug

This repository demonstrates a potential bug related to the order of middleware execution in Express.js applications. Specifically, placing a normal middleware function after an error-handling middleware function will lead to the normal middleware being executed even after an error. 

## Bug Description

The bug arises from incorrect placement of middleware within the Express.js application. The error handling middleware should always be placed at the end to handle any errors that may occur in prior middleware. This example places a normal middleware function after the error handling middleware which will always execute even if an error has occured previously.

## Bug Solution

The solution involves rearranging the middleware functions to ensure correct execution order. The error-handling middleware should always come last. 

## How to reproduce:
1. Clone the repo 
2. Run `npm install`
3. Run `node bug.js`
4. Observe the unexpected response.