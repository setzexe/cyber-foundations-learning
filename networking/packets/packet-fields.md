# Packet Fields

Packet Fields are the individual pieces of information in a packet's header. These fields describe where the packet came from, where it is going, how it should be handled, etc. 

In cybersecurity, packet fields often matter more than payload (data) because these fields show intent and behavior. Is it a malicious packet trying to attack? Is it legit?

## Important Fields

Not every field even is needed to be understood. Most analysis focusing on the bunch that consistently signals malicious / legitimate behavior.

### Source IP Address

This is the IP address of the system sending the packet. It identifies the origin of traffic and is used to detect scanning / brute force.

Things to look out for:

- Many source IPs targetting one service
- Unexpected geographic / internal sources 

### Destination IP Address

This is the IP Address that is receiving the packet. It can identify which system is being attacked.

Look out for traffic trying to access sensitive areas.

### Source Port

A temporary (emphemeral) port the client is using to send data. It can track connection behavior and can help destinguish between clients & sessions.

Watch out for rapid repeated use of ports and any abnormal patterns.

### Destination Port

The service being targetted (22, 80, 443). It directly indicates attacker intent.

Watch out for any attempts to connect with important ports that should NOT be exposed, like admin services.

### Protocol

This defines how the packets should be processed (TCP, ICMP, UDP). These determine connection behavior.

Watch out for any unexpected protocols for certain requests.

### TCP Flags (If TCP)

These are the control bits that describe connection state (SYN, ACK, FIN, RST). These directly reveal handshake behavior and can expose floods and abnormal connections.

Watch out for excessive SYN / RST packets that lack connection.

### Payload Size

The amount of data carried in the packet. These indicate activity type.

Large volumes of small packets and sudden spikes of traffick are red flags.

### Timing and Frequency 

These are not explicit fields, but you will often receive this with packet flow.

Many attacks are pattern based, making this a key field to check out for this (along with automation!) 

___

## Blue Team Relevance

Packet fields are used to:

- Detect attacks before authentication
- Create firewalls and IDS rules
- Correlate logs across systems
- Seperate humans from automation

You often are looking for bad patterns rather than bad individual packets.

## Red Team Relevance 

Attackers work with:

- Source IP Distribution
- Timing
- Handshake Completion
- Port Selection

