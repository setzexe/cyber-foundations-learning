# TCP Handshake

To summarize, TCP (Transmission Control Protocol) is a main protocol you will see on the internet. It ensures reliable, controlled, and error-checked delivery of data between applications. 

The TCP Handshake is the specific process that is used to establish a connection between two systems before data is exchanged. It is a three-step process that ensures both sides are reachable, willing to communicate, and synchronize.

TCP is stateful, meaning both sides track connection state. The handshake creates a shared state out of this.

## The Three Steps

### 1. Syncronize (SYN)

The client initiates a connection by sending a packet with the SYN flag set. The client intends to connect. It sends out a sequence number.

### 2. SYN-ACK (Syncronize + Acknowledge)

The server responds with both:

- SYN (its own sequence number, for identification purposes)
- ACK (Acknowledging the client's SYN)

This step confirms the server is reachable, the destination port is open, and the server is willing to connect.

### ACK (Acknowledge)

The client sends an ACK back to the server, acknowledging the server's SYN. At this point, the connection is established, both sides track connection state, and data transfer can begin.

___

## If a Handshake Fails...

If the handshake does not complete, the connection remains half open. Data transfer does not occur.

This is common to find in port scans, SYN floods, blocked/filtered traffic, etc.

## Relevance to Cybersecurity

Many network attacks rely on abusing / observing handshake behavior. Handshake behavior reveals:

- Whether a port is open, closed, or filtered
- Whether a system tracks connection state
- Whether traffic is legit or automated

Understanding the handshake explains how scanners and floods work.

Seucurity tools often classify traffic as new connection, established connection, or incomplete / abnormal connection. This all relies on the handshake process.

### Relationship to Packet Analysis

Packet analysis relies on handshake understanding to interpret things like SYN packets, SYN-ACK responses, half open connections, etc. 
