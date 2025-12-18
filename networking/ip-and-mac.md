# IP and MAC Addresses

IP & MAC addresses are the two primary ways of identifying devices on a network, allowing for communication. While both important, they serve different purposes.

---

## IP (Internet Protocol) Addresses

An IP Address is an identifier given to a device on a network. It allows data to be routed locally and globally. They can change over time (dynamic assignment), and are required for communication beyond the local network.
- IP's work at the network layer, or layer 3. The local network is layer 2. The physical layer like cables are layer 1.

Cybersecurity mainly works with IPv4 addresses. These hold 2^32 possible addresses, written as four octets that range from 0-255 each.

### Public vs Private IP's
- **Public IP's**: These are assigned by your ISP (Internet Service Provider). They are visible on the internet and are used by servers.

- **Private IP's**: These are used for local networks like a Home WIFI. They can not be directly reached from the internet.

### NAT (Network Address Translation)
NAT allows multiple private devices on a network to share a single public IP. The router rewrites source IP's into public IP's, and responses are mapped back to each device. Be wary: a misconfigured NAT can expose internal services.

## MAC (Media Access Control) Addresses

A MAC address is a hardware-level addressed to a device by the manufacturer. These are used only within a local network (layer two, with data-linking) and does not traverse routers. Routers strip layer 2 information before forwarding packets.

- An example of a MAC address is (a4:c3:f0:85:ac:2d). They are made of 6 octets, 12 hexidecimal digits. The first half identifies the manufacturers. The second half is device-specific.

MAC addresses can be manually changed in software by a process called spoofing. This can bypass weak security protocols and allow unauthorized devices to access a local network. 

### How these interact

When a device sends data, the IP address determines *where* the data goes. The MAC Address determines *which local device* it goes to.

- ARP (Address Resolution Protocol) maps IP addresses to MAC addresses in a local network.
