## Errors

> Error responses return JSON structured like this:

```json
{
  "code": 400,
  "status": "Bad request",
  "message": "The server can not or will not process the request due to an apparent client error."
}
```

The API may return any of the following errors at any time. It is up to you to handle these errors accordingly. To make it easier though, the API also sends a message along with the error.

Be aware that ratelimiting is still enforced, despite any of the following errors being sent (even the `5xx` ones!). It is adviced, in most cases, to implement [exponential backoff](http://en.wikipedia.org/wiki/Exponential_backoff), just to be on the safe side.

All of the described errors refer to 'resources' in their descriptions. These are to be understood as both endpoints and actual files alike.

<aside class="notice">
The servers are operating behind a reverse proxy which enforces very aggressive (IP) banning. It is likely VPNs and Proxies will therefore not function, please use your personally owned IP adresses.

It goes without saying that port-scanning, (D)DOSing and other idiocies will result in permanent and irrevocable bans.
</aside>

The ExoDeus API uses the following error codes:

Code | Status | Description
---- | ------ | ------
400 | Bad Request | The server can not or will not process the request due to an apparent client error. This is the generic error that is sent when none of the following 4xx errors is applicable. This request should not be repeated.
401 | Unauthorized | Authentication is required.
402 | Payment Required | Currently not in use.
403 | Forbidden | The request contained valid data and was understood by the server, but the server is refusing action. This may be due to the user not having the necessary permissions for a resource, or attempting a prohibited action.
404 | Not Found | The requested resource could not be found. This request should not be repeated.
405 | Method Not Allowed | The request method is not supported for the requested resource. For example, a GET request to a resource that requires data to be presented via POST, or a PUT request to a read-only resource. This request should not be repeated.
406 | Not Acceptable | The requested resource is capable of generating only content not acceptable according to the Accept headers sent in the request.
408 | Request Timeout | The server timed out waiting for the request. The client did not produce a request within the time that the server was prepared to wait. This request may be repeated, but faster.
409 | Conflict | The request could not be processed because of conflict in the current state of the resource. This may occur as the requests of two users clash and yours loses.
410 | Gone | The requested resource was previously in use but is no longer available and will not be available again. This resource has been intentionally removed and should not be requested in the future.
413 | Payload Too Large | The request is larger than the server is willing to process.
414 | URI Too Long | The request URI is longer than the server is willing to process.
415 | Unsupported Media Type | The request entity has a media type which the server or resource does not support.
418 | I'm a Teapot | The request for coffee can not be satisfied by a teapot.
426 | Upgrade Required |The client should switch to a different protocol such as TLSv1.3.
429 | Too Many Requests | The client has sent too many requests in a given amount of time. This can also be due to an over-usage of your IP address. Please adopt exponential backoff to avoid banning.
431 | Request Header Fields Too Large | The server is unwilling to process the request because either an individual header field, or all the header fields collectively, are too large.
500 | Internal Server Error | The server can not process the request due to an unexpected server error. This is the generic error that is sent when none of the following 5xx errors is applicable. This request should not be repeated.
501 | Not Implemented | This resource is currently not available, but will probably be in the future. This may also mean that the resource is available on other servers, such as the `development` or the `beta` servers.
502 | Bad Gateway | The server is acting as a reverse proxy and received an invalid response from the upstream server.
503 | Service Unavailable | The server cannot handle the request, either because it is overloaded or down for maintenance. This is a temporary state, please try again later. In the meantime, please adopt exponential backoff. 
504 | Gateway Timeout | The server is acting as a reverse proxy and did not receive a timely response from the upstream server.
505 | HTTP Version Not Supported | The server does not support the HTTP protocol version used in the request.
||
