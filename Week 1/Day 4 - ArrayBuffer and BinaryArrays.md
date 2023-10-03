 # ArrayBuffer and BinaryArrays
ArrayBuffer is a built-in object in JavaScript that represents a generic, fixed-length raw binary data buffer. It allows you to work with low-level binary data in a structured way. The length of an ArrayBuffer cannot be changed once it's created.  

1.Binary Data Storage: ArrayBuffer is used to store binary data, such as integers, floats, or other raw binary data in a structured manner.

2.Fixed Size: The size of an ArrayBuffer is fixed when it is created and cannot be changed.

No Direct Manipulation: You cannot directly read or write data to an ArrayBuffer. Instead, you work with views called TypedArrays to read and write data.

Typed Arrays: Typed Arrays are views that allow reading and writing data in a specific format (e.g., Int8Array, Uint8Array, Int16Array, Float32Array). These views provide a typed interface to the raw binary data stored in the ArrayBuffer.

Usage:

Create an ArrayBuffer using new ArrayBuffer(length), where length is the number of bytes needed for the buffer.
Create a TypedArray (e.g., Int8Array, Uint8Array, etc.) to read and write data to the ArrayBuffer.
The basic binary object is ArrayBuffer – a reference to a fixed-length contiguous memory area.

# fetch

JavaScript can send network requests to the server and load new information whenever is needed.

For example, we can:

Submit an order,

Load user information,

Receive latest updates from the server,

There are multiple ways to send a network request and get information from the server.

The fetch() method is modern and versatile, so we’ll start with it. It evolved for several years and continues to improve, right now the support is pretty solid among browsers.

The basic syntax is:

let promise = fetch(url, [options])

url – the URL to access.

options – optional parameters: method, headers etc.

The browser starts the request right away and returns a promise.

Getting a response is usually a two-stage process.

First, the promise resolves with an object of the built-in Response class as soon as the server responds with headers.

So we can check HTTP status, to see whether it is successful or not, check headers, but don’t have the body yet.

The promise rejects if the fetch was unable to make HTTP-request, e.g. network problems, or there’s no such site. HTTP-errors, even such as 404 or 500, are considered a normal flow.

We can see them in response properties:

· ok – boolean, true if the HTTP status code is 200-299.

status – HTTP status code.
