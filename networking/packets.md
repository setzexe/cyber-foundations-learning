# Packets

A packet is a small unit of data sent over a network. Large data like web pages, messages, and files are often sent packet-by-packet and reassembled at the destination. If you want to load google, you're not just being sent google's home page in it's entirety. You get it in packets, which is reassembled before making it viewable to you.

Networks cannot reliably send large amounts of data at once. This is where packets come in. It makes global communication possible with efficient transmission, error handling, and routing across multiple networks. 

## Packet Contents

Each packet contains:

- source address
- destination address
- data payload (The actual data)
- control information

The payload is the actual data, and the rest helps the network deliver it correctly.

## Packets vs Data

Packets are containers. They are not the data itself. They can carry HTTP requests, DNS queries, file data, authentication information, etc. The packet itself does not understand the data, it simply just transports it.

## Packet Flow 

A single request may involve dozens or hundreds of packets. These are sent independantly and usually arrive to the system out of order. Before you actually see the data, the system reassembles it. So as the user only sees one action, the network handles many packets.

## Reliability and Loss Handling

Packets can be delayed, lost, or arrive out of order. Protocols handle this by retransmitting missing packets or reordering packets correctly. This is an automatic process, the user does not have to do anything.

## Packets and Security

Packets expose where data is going, how much data is being sent, and patterns in packet sending. With encryption, contents are hidden. The metadata, however, still exists. Packet behavior can indicate malicious

Understanding packets helps reasoning about traffic flow, how attacks traverse networks, etc. Packets are the physical reality behind all network communication.

