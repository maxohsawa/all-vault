# The Observer Pattern
![[oberserver-pattern.png]]

- Observers are clients
-   Subject is the model / source that Events happen to
	-   the Subject notifies the Observers
-   pattern is used when a Subject is producing multiple Events that Observers want to be notified about
-   in Node, objects Emit named events that cause Listeners to be called (callbacks)