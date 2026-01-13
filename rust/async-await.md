## Async/Await

We mark a function as asynchronous with the keyword `async`. An `async` function does not return a value immediately, instead it returns a `Future`, representing work which will be completed later. We can only `await` (wait for the `Future` to resolve) inside of asynchronous functions. A *runtime* is something that polls a `Future` to completion, it handles all of the scheduling, I/O, tasks etc. in order to make that happen.
