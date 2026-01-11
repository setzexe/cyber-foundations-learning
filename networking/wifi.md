# WiFi

Wi-Fi is a wireless networking technology that is based on IEEE 802.11 standards. This is a set of protocols and rules so that Wi-Fi can be accessed correctly by different clients. Wi-Fi allows devices to connect to a local network without physical cables. It operates at the physical and data link layers, but carries normal IP packets like Ethernet does. 

## How Wi-Fi works (Device --> Router)

When a device connects to the Wi-Fi, it first discovers nearby access points and chooses one to connect to. The device then associates the access point and does authentication under the network's security. Once authentified, the device receives an IP via DHCP. Once the connection process is complete, traffic flows normally.

Wi-Fi does NOT make your client magically talk to the internet. It is sent to the WiFi first. Traffic flows with the WiFi kind of as a middle man.

## Frequencies & Bands

Most Wi-Fi networks operate on the 2.4 / 5 GHz bands. Bands are just a set of frequencies that Wi-Fi uses for data flow. Band choice directly affects performance and reliability

2.4 GHz has longer range and better wall penetration, but is more congested and slower.

5 GHz offers higher speeds and lower latency but has a shorter range and is more affected by obstacles.

## Signal and Interference 

Wi-Fi performance is heavily influenced by physical factors. Distance from the routers, walls, floors, and building material can lessen a signal. Interference from bluetooth, other Wi-Fi networks, crowded networks, and even microwaves can cause packet loss. Poor Wi-Fi problems often stem from physical conditions.

## Wi-Fi vs Ethernet

Wi-Fi tends to be more for general use. It is flexible and convenient, as you don't need any physical cables. However, it is less reliable than Ethernet due to interference and signal variability.

Ethernet uses physical cables, which gives it a more consistent flow of traffic. Low latency, high speed, minimal packet loss. Servers and security-critical systems almost always use Ethernet due to this.

## Security Basics

Wi-Fi security depends on encryption and authentication. Modern networks use WPA2 or WPA3 to handle the encryption, it protects traffic between devices & the access point. Open / poorly secured networks could allow attackers to manipulate or observe traffic. Even with Wi-Fi, a protocol like HTTPS would still be necessary for application-level networking.

## Common Wi-Fi Threats

Attackers may create fake access points that impersonate legit networks to capture traffic. They could impersonate a cafe's Wi-Fi and track all incoming traffic. They can also exploit weak passwords. Public Wi-Fi is especially risky because the client often times have no control over configuration. Many of these threats target the access layer as opposed to the application layer.

## Cybersecurity Relevance

Wi-Fi controls how a device enters a network, making it part of a vast attack surface. It can cause alot more inconsistency than Ethernet. Knowing Wi-Fi behavior can help differentiate simple Wi-Fi mishaps or legitmate issues.

