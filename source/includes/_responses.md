# Response codes

## Success

> Response JSON structure:

```json
{
  "code": 200,
  "status": "OK",
  "content": {
      "hello": "world"
  }
}
```
> Note that the content can be an object, an array, a string, a boolean, or a mixture of all the previous types.


The API may return any of the following status codes. These are mainly for informative purposes and anything superior to a 200 status rarely requires any acting upon.

The ExoDeus API uses the following status codes:

Code | Status | Description
---- | ------ | ------
200 | OK | Successful request. The response will contain a JSON corresponding to the requested resource.
202 | Accepted | The request has been accepted for processing, but the processing has not been completed. The request might or might not be eventually acted upon, and may be disallowed when processing occurs.
204 | No Content | The server successfully processed the request, and is not returning any content.