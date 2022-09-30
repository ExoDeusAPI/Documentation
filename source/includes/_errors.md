# Errors

<aside class="notice">
The API may return any of the following errors at any time. It is up to you to handle these errors accordingly. To make it easier though, the API also sends a message, as a plain string, along with the error.

Be aware that ratelimiting is still enforced, despite any of the following errors. It is adviced, in most cases, to implement [exponential backoff](https://en.wikipedia.org/wiki/Exponential_backoff), just to be on the safe side.
</aside>

The ExoDeus API uses the following error codes:


Error Code | Meaning
---------- | -------
503 | Service Unavailable -- The server cannot handle the request (because it is overloaded or down for maintenance). This is a temporary state, please try again later.
