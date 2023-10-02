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