# FILE OBJECT
+ A file object inherits from Blob and is extended with filesystem related capabilities. There are two ways to obtain it. 

<b>First there is a constructor, similar to Blob:</b>

new File(fileParts, fileName, [options])

+ + <b>fileParts</b> - is an array of Blob/BufferSource/String values.  
+ + <b>fileName</b> - file name string.
+ + <b>options</b> - optional object:
+ + <b>lastModified</b> - the timestamp (integer date) of last modification

<b>Second, more often we get a file from <input type="file"> or drag’n’drop or other browser interfaces. In that case, the file gets this information from OS</b>

+ As File inherits from Blob, File objects have the same properties, plus:name – the file name,

+ lastModified – the timestamp of last modification

+ That’s how we can get a File object from <input type="file">:

## FILE READER
FileReader is an object with the sole purpose of reading data from Blob (and hence File too) objects. It delivers the data using events as reading from disk may take time.

The constructor is as follows:

+ let reader = new FileReader(); // no arguments

### The main method is as follows:

+ <b>readAsArrayBuffer(blob)</b> – read the data in binary format ArrayBuffer.
readAsText(blob, [encoding]) – read the data as a text string with the given encoding (utf-8by default).
+ <b>readAsDataURL(blob)</b> – read the binary data and encode it as base64 data url.

 + <b>abort()</b>– cancel the operation.

The choice of read method depends on which format we prefer, how we are going to use data.

+ <b>readAsArrayBuffer</b> – for binary files, to do low-level binary operations. For high-level operations, like slicing, File inherits from Blob, so we can call them directly, without reading.

+ <b>readAsText</b> – for text files, when we’d like to get a string.

+ <b>readAsDataURL</b> – when we’d like to use this data in src for img or another tag. There’s an alternative to reading a file for that, as discussed in chapter Blob: URL.createObjectURL(file).

As the reading proceeds, there are events:

+ <b>loadstart</b> – loading started.

+ <b>progress</b> – occurs during reading.

<b>load</b> – no errors, reading complete.

<b>abort</b> – abort() called.

<b>error</b> – error has occurred.

<b>loadend</b> – reading finished with either success or failure.

When the reading is finished, we can access the result as:

+ reader.result is the result (if successful)

+ reader.error is the error (if failed).
The most widely used events are for sure load and error.


