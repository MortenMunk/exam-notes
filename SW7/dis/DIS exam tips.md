Start with what and why is it important
explain system model
describe one or two algorithms

**Lec 4:**
Choose either:
- centralized algorithm
- Token ring algorithm
And:
- ricart Argrwala
- Maekwa

Skip crash detection


**Lec 5**:
- Discuss ISIS a little (not too much time)
	- Causal maneuver and lamport clocks
	- Describe below figure![[Pasted image 20241003142017.png]]

**Lec 6**:
- Mutex requires very good presentation
- Consensus is harder to discuss both byzantine, equivalence, f-sync-resilient, f-byzantine, etc. 

Consensus = 2 minutes about context, why it is important
	- then Equivalence, byzantine failures, impossibility results (about 4 minutes)
	- f-crashes resilient
	- f-king (brug eksempel fra tavlen)
	- Paxsos or Raft without detailed algorithm

**Lec 7:**
Show different consistency (strong, weak, causual)
Active replication (VIGTIGT AT FORSTÅ FORSKELLEN PÅ REPLICATIONS, eg. active, passive)
General idea/discussion of gossip architecture
something general about elections (block and read, timestamp)
maybe some vector clocks

**Lec8**
Merkle trees are optional
Describe how the blockchain works
Consensus (Proof of work)
Miners and what they do
Maybe transaction checking
Longest chain wins.

**Lec9**
Be able to explain chord in a structured p2p network

**Lec10**
very light on mac layers or not. it depends on you
Discuss about Tree Routing and Cskip
DSR and differences between tree routing
Star network, tree network, mesh network

**Lec11**
GFS architecture & passive replication
What if master fails (checkpoint, logfiles etc.)
Why do I need chubby
Difference between masters