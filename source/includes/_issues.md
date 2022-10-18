# Known issues

## Incorrect redirect

In some instances using the `http` endpoint may be buggy. More specifically, the method of the request and (some) of its content maybe altered and/or lost when the reverse proxy redirects your `http` request to `https`.

We therefore strongly recommend to use the https endpoint directly.