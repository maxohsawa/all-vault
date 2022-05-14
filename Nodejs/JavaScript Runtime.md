# JavaScript Runtime
![[javascript-runtime.png]]

- [[javascript engine]] is single threaded, but javascript runtime enables multi-threading
- javascript runtimes include a Web API
	- send HTTP requests
	- listens to DOM events	- timing execution (setTimeout, setInterval)
	- caching, database storage
- web APIs are asynchronous
- tasks are added to the callback queue
- when the javascript engine call stack is empty, the event loop hands over the next task from the callback queue
- [philip roberts talk on event loop](https://www.youtube.com/watch?v=8aGhZQkoFbQ)
- visualization tool [loupe](http://latentflip.com/loupe/)
- nodejs runtime is similar to a browser javascript runtime, but with added functionality like interacting with the operating system and accessing system resources

#javascriptruntime #javascriptengine #eventloop #callbackqueue #asynchronous #multithreading