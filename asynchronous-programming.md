### Asynchronous Programming

> In a synchronous programming model, things happen one at a time.
> - ...Drawback: the second request will be started only when the first has finished. The total time taken will be at least the sum of the two response times.
> The solution to this problem, in a synchronous system, is to start additional threads of control.
> A second thread could start the second request, and then both threads wait for their results to come back, after which they resynchronize to combine their results.
> Both prominent JavaScript programming platforms—browsers and Node.js—make operations that might take a while asynchronous, rather than relying on threads.
https://eloquentjavascript.net/11_async.html

> An asynchronous model allows multiple things to happen at the same time.
> callback: async functions that need to wait for something take an extra argument
> promises: asynch functions that return an object that represents its (future) result instead of passing around callback functions.
https://eloquentjavascript.net/11_async.html

> A promise is a receipt representing a value that may not be available yet.
> It provides a then method that allows you to register a function that should be called when the action for which it is waiting finishes.
> - you can “chain” multiple calls to then together to set up a sequence of asynchronous actions.
```
function randomFile(listFile) {
  return textFile(listFile)
    .then(content => content.trim().split("\n"))
    .then(ls => ls[Math.floor(Math.random() * ls.length)])
    .then(filename => textFile(filename));
}
```
https://eloquentjavascript.net/11_async.html

### Promise.Resolve
> The easiest way to create a promise is by calling Promise.resolve. This function ensures that the value you give it is wrapped in a promise. If it’s already a promise, it is simply returned. Otherwise, you get a new promise that immediately resolves with your value as its result.
https://eloquentjavascript.net/11_async.html

### Async/Await
> Async/await is a syntactic sugar on top of promises. It provides a more concise way to write asynchronous code, making it easier to read and write. With Async/Await, you can write asynchronous code that looks similar to synchronous code, and it uses promises under the hood.
https://medium.com/version-1/difference-between-promise-and-async-await-95e453182f55
