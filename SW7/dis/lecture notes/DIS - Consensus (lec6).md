Group of processes agree on one and only one value

practial applications:
- replication (ledgers, and distributed file systems)
- redundancy (e.g. space and aeronautic systems)

Byzantine
- evil or faulty

impossibility in async systems
- informally (communication can be blocked indefinetely)
- Reliable TO multicast also impossible in async

Requirements for consensus
- Termination = eventually a correct process sets its decision variable d_i
- Agreement = the decision values of all correct processes are the same
- Integrity = If all correct processes propose the same value, then any correct process in the decided state decide on that value
Other integreties
	- Weak integrity = the agreed value must be one proposed by a correct process

Byzantine Consensus
- Byzantine integrity = if all non-faulty processes start with the same value, then all non-faulty processes decide on that value
	- This time the faults comprise sending "wrong" messages

Three equivalent problems
- Consensus
- Byzantine generals
	- One commander issues the order, the lieutenants 
	- Termination: Eventually each correct process sets its decision variable 
	- Agreement: The decision variable of all correct processes are the same 
	- Integrity: If the commander is correct, then all correct processes decide on the value that the commander proposed. 
		- Note that, for the Byzantine generals problem, integrity implies agreement when the commander is correct; but the commander could be faulty
- Interactive Consistency 
	- Every process proposes a single value. Goal: agreeing on a vector of values, one for each process 
	- Termination: Eventually each correct process sets its decision variable 
	- Agreement: The decision vectors of all correct processes are the same 
	- Integrity: If process p_i is correct, then all correct processes decide on v_i as the ith component of their vector
- Raft is used in many blockchains
- Paxos is by google for distributed lock service and others for distributed data storage