# Reading Packets

As mentioned in the README.md, packets work the communication of the internet. Web requests, DNS, scans, etc are broken into packets before transmission. Packets are the lowest level observable form of network activity. There are two distinct parts of a packet:

- Headers, which is the metadata about the communication
- Payload, the actual data being sent

Packets show what is actually happening on a network. You can determine who is communicating from whatever protocol, what action is being attempted, and if their behavior is legit / suspicious. Pockets are the ground truth behind logs, alerts, and tools.

___

Reading Packets **does not** mean decoding raw hex by default. In practice, packet analyzing focuses on flags like:

- source & destination IPs
- source & destination ports
- protocol (ICMP, TCP, UDP, etc)
- flags & control fields
- payload size & structure
- frequency & timing patterns

Most packet analysis and insight focuses on patterns rather than raw content itself. 

## Wireshark

The tool that you will use for understanding packets (as raw data is very hard to understand) is **Wireshark.** It takes all incoming packets and translates them into human readable text, while also giving out indicators like source / destination IP & ports, protocol, etc. 

## Core Questions to Ask When Reading Packets

When analyzing traffic, you can always ask these to get a bigger view of the picture:

- Who is sending the packet, and who/where is it being received? 
- Which protocol is in use?
- Why is this packet being sent? Is this normal for the system/network?

Suspicious activity relies moreso on context rather than malformed data.

## Packet Example (Simplified)

    Source IP: 192.168.1.25
    Destination IP: 10.0.0.8
    Protocol: TCP
    Source Port: 54321
    Destination Port: 22
    Flags: SYN

The packet is from a private network, sent from a higher client-side port and is trying to access our SSH, aka remote admin access. The packet uses TCP.

From a cybersecurity perspective, you would look at the context from this. It would be normal if sent from an admin workstation, but suspicious if sent from a web server. And even more suspicious if this packet is repeated from multiple sources.

## Common Red Flags

Indicators often include:

- unexpected protocol's for a system's role
- traffic to unusual ports
- repeated connection attempts
- malformed / incomplete handshakes
- sudden changes in traffic volume/direction

These patterns often precede an attacks. The attackers are testing the attack surface.

___

Packets explain why logs exists, how alerts are triggered, and what security systems like IDS and firewalls observe.

Understanding packets makes higher-level security much more understandable.



