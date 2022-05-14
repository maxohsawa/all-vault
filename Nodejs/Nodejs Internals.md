# Nodejs Internals
![[nodejs-environment.png]]

## Nodejs environment
- examples of nodejs APIs
	- file system
	- http requests
	- paths
	- crypto
- nodejs bindings are used to call C/C++ implementations
- libuv handles I/O tasks and is written in low level language and is highly optimized
	- nodejs API -- fs (javascript) --> nodejs binding --> libuv (C++) --> OS
	- libuv does asynchronous I/O

## Nodejs codebase
- lib folder containsnodejs APIs written in javascript
- src folder contians nodejs bindings written in javascript and C++

## libuv codebase
- src folder contains the bulk of the code
- nodejs bindings reference function in libuv