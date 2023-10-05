The terms "simple request" and "non-simple request" are related to the same-origin policy and CORS (Cross-Origin Resource Sharing) in web development.

Simple Request:
A simple request is an HTTP request that meets specific criteria and is considered safe according to the CORS policy. For a request to be considered simple, it must meet all of the following conditions:
Uses only allowed methods: GET, HEAD, POST

Uses only allowed headers:

Accept
Accept-Language
Content-Language
Content-Type (with a value of application/x-www-form-urlencoded, multipart/form-data, or text/plain)
The Content-Type header mentioned above must have one of the allowed values.

Simple requests are sent directly without a preflight request (OPTIONS). The server can respond to these requests without additional CORS headers, or with simple CORS headers.

Non-Simple (or Preflighted) Request:
A non-simple request is an HTTP request that doesn't meet the criteria for a simple request. For example, if it uses an HTTP method other than GET, HEAD, or POST, or if it uses custom headers other than the allowed headers, it is considered a non-simple request.
In the case of a non-simple request, the browser sends a preflight request using the OPTIONS method to the server before the actual request. The purpose of the preflight request is to determine whether the actual request is safe to send and what headers and methods are allowed by the server.

The server must respond to the preflight request with appropriate CORS headers (e.g., Access-Control-Allow-Origin, Access-Control-Allow-Methods) to indicate whether the actual request is allowed from the origin specified in the request.

In summary, simple requests follow a set of specific conditions and can be sent directly, while non-simple requests require a preflight request to ensure they are safe and allowed by the server.


### What happens to the browser if the request is cross origin?

When a web application sends a request from a browser to a different origin (a different domain, protocol, or port), it is considered a cross-origin request. Depending on the type of request (simple or non-simple) and the server's CORS (Cross-Origin Resource Sharing) policy, different things can happen:

Simple Cross-Origin Request:

If the request is a simple cross-origin request and the server supports CORS for that request, the browser sends the request directly.
If the server allows cross-origin requests from the specific origin (defined by the Origin header), the server includes appropriate CORS headers in the response (e.g., Access-Control-Allow-Origin, Access-Control-Allow-Methods, etc.).
The browser then allows the response to be accessed by the requesting script if the CORS headers indicate so.
Non-Simple (Preflighted) Cross-Origin Request:

If the request is a non-simple cross-origin request (e.g., it uses methods other than GET, HEAD, POST, or includes custom headers), the browser first sends a preflight request using the OPTIONS method to the server.
The purpose of the preflight request is to ask the server if the actual request is allowed based on the CORS policy.
The server responds to the preflight request with appropriate CORS headers indicating whether the actual request is allowed or not.
If the server allows the actual request, the browser sends the actual request (e.g., GET, POST) with the original headers.
Blocked Request:

If the server does not include the necessary CORS headers and the request is not a simple request, the browser blocks the request and the JavaScript code in the page won't be able to access the response.
This is due to the same-origin policy, which restricts scripts from accessing resources across different origins for security reasons.
In summary, the behavior of the browser when handling a cross-origin request depends on whether the request is simple or non-simple, and whether the server supports and allows CORS for the given request. If the request is not allowed by the server's CORS policy, the browser will block access to the response to maintain security.