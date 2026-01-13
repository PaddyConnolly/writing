## Future

Asynchronous programming in Rust is basically built on top of Future. A future is simply a computation which doesn't have a value yet. All futures have a `poll` method which lets us do a little more work towards generating the value. Futures in Rust are lazy, if we don't `poll` them, they may never complete.

This introduces a small problem, what if we want to call a function that is asynchronous in `main`?. This would mean `main` itself would have to be asynchronous. But we don't have a function which automatically polls `main`, so it may never finish.

`tokio::spawn` is a useful function here - it hands over a `Future` to the `tokio` runtime for polling, without waiting for its completion like an `await` would. Consider if we started a server, this is asynchronous. If we waited for its completion, we would wait for the server to go down, which would mean we never get a chance to use our code to interact with the server.
