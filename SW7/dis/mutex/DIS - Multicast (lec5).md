one process casts to many
one to many multicast:
- streaming

many-to-many multicast:
- skype

Closed groups:
- only members of specific groups can send messages

If you multicast, you yourself will receive the message

IP multicast:
- IGMP protocol to associate with address
- Send and receive from address
- Built on UDP over IP
- IGMP is now supported by firewalls

UDP
- No guarantees
- no retransmission
- only one attempt
- messages delivered in arbitrary order

Requirements
- Assume:
	- reliable 1:1 communication
	- sender might crash
	- no order
- We want to guarantee
	- messages are sent exactly once if sent.
	- messages are eventually delivered to non-crashed process

Reliable multicast properties
- integrity
	- Each message is delivered at most once
- Validity
	- A process delivers itself or crashes
- Agreement
	- All correct processes deliver or no correct process deliver

- runtime is O(N²)


Reliable multicast over IP
- sequence numbers
	- duplicates and lost messages
- "hold-back" construction
	- wait for re-transmission
	- replication of messages
- We can keep track of lost messages by using the sequence numbers (e.g if a number is missing, we must re-transmit message)

- Integrity (IP uses checksum)
- Validity
- agreement (not really)
- no drops, good ordering = O(N)
	- You can bombard with messages, while still waiting for the missing sequence number

Ordered multicasts
- FIFO Ordered
	- messages are received in order they are sent
	- De kan dog godt interweaves
- Total Ordrered
	- order kan være random
	- Men sendes i samme order til alle
- Causally Ordered
	- Happened-before principle

IP
- Receiver holds the queue
- Causal ordering implies FIFO

Reliable multicast over IP is fifo
- because we respect sequence number of senders

Totally ordered sequencer
- bottle-neck
- single point of failure

Vector clocks
- vector of timestamps
- Everytime i send, I add a timestamp to my vector, but i also update the vector from which i received