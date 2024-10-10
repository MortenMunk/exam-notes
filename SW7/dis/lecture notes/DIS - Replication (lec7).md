CAP Theorem
- you can only satisfy two of the three properties
- Properties:
	- Consistency
		- Bank account is same, regardless of server
	- Availability
		- Bank account is always accessible, no delays
	- Partition tolerance
		- Loss of connection will not disturb service
		- Either drop availability = indefinite wait
		- or drop consistency = inconsistent answers
	
- CP systems
	- Financial sector
	- simulation
	- Core/critical services are often CP
- AP systems
	- Seach engines
	- emails
	- social networks
- CA systems
	- Single server system
	- Modern cpu

General workflow
1. Request
2. Coordination
3. Execution 
4. Agreement 
5. Response

Fault tolerance
- f-resilient replication
- no downtime
- transparent to clients

Transparent = client does not need to now how replication is done.

Strong consistency
- in real-time, after update A, everybody will see the modification done by A when reading

Eventual consistency
- does not force immediate updates across all nodes
- changes reflect everywhere after a delay
- drawbacks: you are often dealing with outdated information. Usually, last write wins

Weak consistency
- Strong availability 
- “reasonably consistent”

Inconsistency


Desired Temporal Consistencies
- If i write a value, i will see that or a newer value on a subsequent read
- If i read twice, the value returned on the second read is at least as new as from the first read
- If data is related (questions and answers), I expect this to be reflected in a consistent manner

linearization
- implementation
	- sync hardware clocks on multiple machines
	- guess maximal network delay D
- Drawback
	- No accurate clock sync algorithm
		- Reasonable versions exist though (depends on D)
	- No hard deadline in async setting

read-only replication
- immutable files
- cache-servers

passive replication (primary/secondary)
- high consistency
- banks?

active replication
- fast failover mechanism
- workload distribution

1. Request: Fs totally ordered reliable multicast to all replicas (and Fs) 
2. Coordination: Requests delivered in total order 
3. Execution: Execute as received 
4. Agreement: Not needed 
5. Response: Byzantine, wait for (n/2) agreements, otherwise send first response.

Passive Replication
1. Request: Through primary replica 
2. Coordination: Primary dictates 
3. Execution: Apply to primary 
4. Agreement: Send value to backups 
5. Response: Reply after backups ACK

- "Just follow primary"
- up to n-1 crashes
- Does not tolerate byzantine failure on the primary replica
- linearizable (with clock of primary)
- large overhead of failure


Gossip architecture
- always receive data that is as old as the current data, or newer
- Causal ordering
- slow read, slow query, fast update
