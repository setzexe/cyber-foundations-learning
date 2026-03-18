# DHCP

DHCP **(Dynamic Host Configuration Protocol)** is the networking service that automatically gives your device the ability, via an "identity", to talk to other devices on a network. 

DHCP works similar to a hotel's front desk.

- You walk in (Connect to WiFi)
- You ask for a room (request network access)
- The front desk gives you your room key + directions + services (IP address + gateway + DNS)

DHCP hear works as the front desk before you can actually utilize the hotel.

When a device wants to access a network, it needs configuration (IP address, gateway, etc) so that it can be differentiated and acknowledged. Without it, users might need to manually do this. It also might cause two devices to have to same IP, which could be catastrophic. DHCP naturally avoid this and makes network accessibility very easy.

## The DHCP Process (DORA)

There are four steps in the DHCP process. They follow the acronym **DORA**.

### Discover

Your device first broadcasts a message (to everyone on a network) looking for an IP address. It intently searches for a DHCP server.

### Offer

The DHCP offers available IP addresses, as well as their lease time & network settings.

### Request

Your device requests one of these IPs.

### Acknowledge (ACK)

The DHCP server confirms that you have officially joined the network.

## What DHCP gives you

When the DORA process is finished, your device now has:

- IP Address (your identity on the network)
- Subnet Mask (defines your local network)
- Default Gateway (your internet exit)
- DNS Server (how you turn domains into IP's)

## Lease Time

DHCP leases are not forever. IP's are leased at limited times set by the server.

Halfway through, your device asks if it can keep using the IP. Usually, this is the case and you keep the IP. Otherwise, you get a new IP.

# Cybersecurity Relevance

Dynamic Host Control Protocol has many exploits.

## Fake DHCP server 

On a public network, an attacker can set up a fake DHCP server. This means that any devices trying to access the network might access this instead of a legit one.

Unsuspecting devices might be given a faulty IP, DNS, gateway, and so on. These can be used maliciously to redirect websites, monitor traffic, read credentials, etc.

Sometime's this is done after a **DHCP DoS Attack**.

## DHCP DoS Attack

Attackers flood HDCP with fake requests. This consumes all available IPs, leaving no proper ones for regular users to use. 

As mentioned earlier, this can be paired with a fake DHCP server. Since other devices won't be able to discover the proper DHCP server, it goes to a malicious one.

It is worth noting that **it is possible for a network to only allow authorized DHCP networks.**



