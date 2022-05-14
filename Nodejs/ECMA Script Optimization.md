# ECMA Script Optimization
-   Avoid using:
	-   eval()
	-   arguments
	-   for in
	-   with
	-   delete
-   inline caching
	-   compiler replaces repetitive references with the actual data
-   hidden classes
	-   if objects are strictly existing by their defined properties then the compiler can use hidden classes to optimize code
	-   adding or deleting properties non-uniformly across objects will prevent compiler from being able to use this optimization

#ecmascript #optimization