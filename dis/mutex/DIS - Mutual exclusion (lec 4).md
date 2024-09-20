mutual exclusion = algorithm to ensure one process occurs at a time
eg. 
- printing
- writing a file
- wireless/wired communication

Properties of good mutex:
- safety
	- at most one process is given access
- liveness (no deadlocks, we do not get stuck)
	- a request for access are (eventually) granted
- fairness/ordering
	- request A happened-before B

Bad mutex (but safe):
- gives nobody access

computation = fast, communication = low

process crash = stays dead

Direct communication = e.g. A wants to talk to B which is two processes, no forwarding

Reliable communication 
- Synchronous
	- Delivery in fixed timerate
- Async
	- Delivery at some point
	- underlying protocol handles re-transmission

Mutex algorithm properties:
- Fault tolerance
- Performance
	- Message complexity
	- Client delay
	- Synchronization delay

Centralized algorithm
- properties:
	- safe = it grants only one at a time
	- liveness = eventually we will receive the mutex
	- Not ordering
- fault tolerance: deadlock if: 
	- coordinator or mutex holder or process in waiting list fails

Token Ring algorithm
- send token around in a ring (which assumes ordering of processes)
- Those who have the token, has the mutex
- forward token to next, if not using mutex
- properties:
	- Safe = grants one at a time
	- Liveness = eventually gets mutex
	- Not ordering = because of the ring structure (e.g. A has token, E wants it, but in the meantime C also wants it, therefore E does not get it before C)
	- fault tolerance = if one process crash, the token cannot be transferred 
		- Deadlock if any process fails
