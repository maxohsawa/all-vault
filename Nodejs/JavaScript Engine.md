# Javascript Engine
-   javascript is single threaded
-   uses a callback queue
-   interpreted language
-   JavaScript created by Brendan Eich
	-   also created the first engine called SpiderMonkey
	-   later co-founded Mozilla where the engine is used in Firefox to this day

![](https://lh6.googleusercontent.com/QadwkZ6rw03p8-gPmVlziEQFSYo19wD25AiXxGHNc57AEspg7POtctJfGrnEaDPJtD3WqUfMNwUQIZKMYb45bFI2LWhtaejtrIzIqn7-GIWMIHcMt6LmNHfPHtkKW3EsQ8AYsruF74O8fijoGg)

-   Components
	-   Parser: parses source text
	-   AST: abstract syntax tree, attempts to make sense of the parsed text
	-   Interpreter: interprets code line by line and generates bytecode, machine instructions in real time
	-   Profiler: in a JIT compiler scheme, it analyzes interpreted code during runtime to determine how it can be optimized
	-   Compiler: takes in all the code then produces optimized machine code all at once
	-   Optimized Code: code that is processed to be as simple as possible
	-   Bytecode: not as low as machine code but engine can finalize to machine code
	-   JIT Compiler: just-in-time compiler, a combination of interpreter and compiler
		-   code is first sent to interpreter (V8: Ignition)
		-   profiler / monitor analyzes code as it is running through interpreter to determine ways to optimize
		-   parts of code that can be optimized get sent to compiler (V8: TurboFan), just in time
		-   optimized code is integrated with bytecode from interpreter
		-   results in execution that accelerates
-   ECMAScript provides a standard for engines so that JavaScript behaves consistently

#javascriptengine #brendaneich #spidermonkey #mozilla #firefox #jitcompiler