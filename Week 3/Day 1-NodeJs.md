# What is Node.js?
Node.js is an open-source, server-side JavaScript runtime environment that allows developers to run JavaScript on the server. It's built on the V8 JavaScript engine from Chrome, enabling it to execute JavaScript code outside of a web browser.

In Node.js, a server is a program that listens for incoming network requests (usually HTTP requests) and responds to those requests accordingly. Servers built with Node.js are often used to handle backend logic and serve data or content to clients, which are typically web browsers or other applications.

 ## HTTP Module: <br>
The http module in Node.js is a core module that provides the basic functionality needed to create an HTTP server. This module allows you to create a server, handle HTTP requests, and send back HTTP responses.

## Creating an HTTP Server:
To create an HTTP server, you use the http.createServer method, passing a callback function that will be called whenever a request is made to the server. This callback function defines how the server handles each incoming request.


```javascript
const http = require('http');
const hostname = '127.0.0.1';
const port = 3000;
const server = http.createServer((req, res) => {
  res.statusCode = 200;
  res.setHeader('Content-Type', 'text/plain');
  res.end('Hello World\n');
});
server.listen(port, hostname, () => {
  console.log(`Server running at http://${hostname}:${port}/`);
});'''