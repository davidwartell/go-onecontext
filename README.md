# go-observer

Merge multiple context.Context.  I have run across a need for this at least two dozen times.  A common case is when you 
need to cleanly shutdown an HTTP server in go and you need a way to interrupt all the requests no matter their state.  
And at same time have individual contexts per request.
At start of each request by merging the globalHTTPServerCtx and your request based ctx you get the result.

This is a derivitive work of https://github.com/teivah/onecontext/ - I found some defects under higher rates of events 
and ended up rewriting parts of it.

## Usage

Example
```go
ctx, cancel := onecontext.Merge(ctx1, ctx2)
```

## Contributing

Happy to accept PRs.

# Author

**davidwartell**

* <http://github.com/davidwartell>
* <http://linkedin.com/in/wartell>
