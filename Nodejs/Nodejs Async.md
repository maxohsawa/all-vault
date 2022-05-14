# Nodejs Async
![[nodejs-async.png]]

## Threads
-   process memory space houses the executable code as well as the call stacks for threads
-   JavaScript is synchronous and Node.js allows it to behave asynchronously and make use of multi-threading
-   Node.js abstract away a lot of the complexities of multi-threaded programming
-   Node uses one made thread which runs the V8 engine as well as the Event Loop which is a part of libuv
-   The asynchronous I/O that libuv handles basically breaks down into two types:
	-   file system
		-   libuv makes use of its thread pool to handle file I/O
	-   network
		-   libuv passes operation on to the operating system to handle network operations
-   Thread pool contains the main thread as well as other threads that are available to take on work
-   File system tasks come through Node.js bindings to libuv
	-   libuv then assigns task to available thread in the thread pool
	-   once task completes, thread returns result to Event Loop which calls the corresponding callback
-   where possible Node.js minimizes the use of threads and instead passes work to the operating system kernel which is already optimized for doing things like network related tasks

## Event Loop
-   Callback Queue
-   when async function completes running, any callback function are added to the callback queue
-   Even loop actually consists of multiple queues which correspond to phases, different categories of events
-   Event Loop Phases
	-   timers
	-   I/O callbacks
	-   setImmediate
	-   close callbacks
-   One tick of the Event Loop consists of completing all the tasks on each queue in sequence

#async #asynchronous #threads #threading #eventloop