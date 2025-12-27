# Network Traffic Flow

## High-Level Flow

When a client communicates with a server, traffic follows this path:

- Data is split into packets
- Packets travel across the network
- Packets arrive at the IP address
- A port determines the destination source
- A process receives the data
- The application pricesses the request
- A response is generated and sent back.

The user sees this extremely fast as one action.

## Step-By-Step

### 1. Data Creation

An application creates data. A web request, command, file transfer, etc. The data is not yet network traffic.

### 2. Packetization

The data is split into packets. Each packet contains routing information and a piece of the data. These packets can travel independently.

### 3. Network Transit

Packets move across routers, switches, and multiple networks. The network does NOT understand the data's meaning; it's job is merely to just transport packets.

### 4. IP Addressing

Packets arrive at the destination IP addresses. The IP identifies the machine, not the service.

### 5. Port Routing

The port number determines which service should receive the data. Only services listening to that port will accept the traffic.

### 6. Process Handling

A running process is bound to the port and receives the reassembled data. This process is usually a web server, a database, or a system service.

### 7. Application Log

The application interprets the data, applies logic, performs actions, and generates a response.

**Most security issues occur here.**

### 8. Response Flow

The response becomes data and is split into packets. You return data the same way as you receive data: through the flow of packets. The client receives and reassembles the response.

## Cybersecurity Use

Networking layers do not enforce trust. There could be input vaidation or false authentication checks. Understanding the traffic flow allows one to trace attacks logically, understand where failures occur, and reason with logs and alerts.