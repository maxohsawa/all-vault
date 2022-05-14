# Call Stack & Memory Heap
## Call Stack
- where execution information is stored
- keeps track of where in the code the execution is

#callstack

## Memory Heap
- where variable and object information is stored
- where memory allocation happens

#memoryheap #memoryallocation

## Stack Overflow
- call stack grows to the point that there is no memory left
- also the name of a popular discussion board for software related topics

#stackoverflow

## Garbage Collection
- uses something like mark and sweep where references and values that have a valid pointer are marked as needed, and the garbage collector sweeps through and removes everything else

#garbagecollection

## Memory Leaks
- race condition where the heap will eventually overflow
	- avoid using global variables unnecessarily
	- remember to remove event listeners after done listening
	- setInterval with objects inside the function will cause a memory leak unless the interval is terminated

## Single threaded
- javascript is a single threaded programming language
- javascript engine is single threaded