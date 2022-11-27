# Introduction

Welcome to the ExoDeus API.

This documentation is a work in progress.

## Rules

### Ratelimits

There is a global ratelimit of 60 requests/minute, which applies to each endpoint. If a more restrictive ratelimit is in place on an endpoint, it will be specified in the documentation. All ratelimits are enforced in a "smooth" manner. You cannot use 60 requests in one second and then wait for 59 more to start requesting again. Formally speaking: 60r/minute === 1r/second.

It is your responsibility to not overstep these limits. Repeated offenses will result in a ban.
