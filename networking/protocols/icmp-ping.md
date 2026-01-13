# ICMP + Ping

The Internet Control Message Protocol (ICMP) is the network layer protocol used for detecting network connection and issues. It does not send or transport any data, it just confirms if there is a connection along with connection speed. This makes it crucial for testing.

## What ICMP Is Used For

A main reason that ICMP is used is for error handling. When a packet is not received due to error, the ICMP generates a packet to send to the sending client. 

Another reason that ICMP is used is for network connectivity diagnostics. To confirm a server's connectivity, a **ping** packet is sent. If successful, it will respond back with a ping time. If it fails, connectivity might not be possible. 

## Ping

Ping is a tool that ICMP uses to check connectivity. It sends ICMP packets (echo requests) and determines the speed it takes to reach the server, back to the client. 

As mentioned earlier, this does not track or deliver any form of data. But it is good for testing latency, which is the time it takes for data to get from one point to another. Lower ping is ideal and what you would find on video calls or online games. High ping is never ideal.

## How It Works

ICMP is a connectionless protocol. It does not require some form of connection before sending an ICMP packet to a device. 

ICMP does not allow targeting of a specific port.

## Attacks 

These attacks, although not necessarily catastropic, are involved with ICMP and Ping.

### ICMP Flood Attack

This is more known as a **DDoS** attack. A client will send overwhelming amounts of pings to target. Because every ping has to be processed & responded to, the computer uses all it's resources to do this until legitimate users are affected on the target's server / computer. 

### Ping Of Death

This happens when a threat sends an abnormally sized packet to a target. When the target's client tries to recompile it, it is too big for the buffer to handle and the computer crashes.

This is alot more susceptible to older systems. Most modern defenses handle this.