mutual exclusion = algorithm to ensure one process occurs at a time e.g. 
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

Ricart and Agrawala algorithm
- Order events
	- Extension of shared priority queue
- request all for grant and wait for all to grant
- Lamport Clocks
	- A can get mutex from B if request happens in clock before B
	- Then clock updates e.g from 1 to 3.
	- B asked for mutex at 2 but cannot get it.
	- therefore they cannot grant each other mutex (except for first time)
- Properties:
	- safe
	- liveness
	- ordering
- fault tolerance
	- If one process fails, then there is not enough grants = deadlock

Maekawas Algorithm
- concept
	- Only communicate with subset
	- pick subset cleverly
	- Ask everyone in subset for access, wait for access grant
- Maekawa only works with one requests at a time (synchronous)
- Deadlock can happen with three processes (in synchronous system)
- Properties:
	- Safe
	- Liveness
	- Ordering (only for synchronous)
- fault tolerance = if one dies in voting set, then deadlock

Heartbeat in synchronized systems
- Assume transmission delay D
- send beat for every T seconds
- Declare dead if no response in T+D seconds

Heartbeat in Async systems
- Guess a D
- Send beat every T seconds
- Dead if not observed in T+D seconds
- If D is too small = alive can be reported dead
- If D is too large = dead can be reported as alive
- We can only suspect crash