# UDP

UDP, or User Datagram Protocol, is another type of data exchanging protocol. Unlike TCP, which ceates a connection and ensures all data is made across, UDP is used a lot more for time-sensitive events like video games, video calling, or DNS lookup. It does this by not forming a connection between devices before sending data. As there is no reliable connection, UDP makes information prone to data loss, although it would not be at extremely big noticeable scales. Like TCP, UDP also is vulnerable to DDoS attacks.

## How UDP Works

The UDP protocol works as simple as just sending datagrams to a larger computer. UDP packets are referred to as datagrams. UDP sends the datagrams in order and checks if any did not send. No connection is made, information is simply just sent.

## TCP vs UDP

TCP is a lot more trusted when it comes to more important data transfers. Anything that might require as much correct data and does not need INSTANT delivery would use TCP. This is also because TCP has the handshake system, creating a connection between devices. You would receive every packet sent, as TCP also verifies if any packets were lost.

UDP ignores this handshake connection and only focuses on sending data. This would be better for things like online games or video calling where it is okay if a datagram or two is lost. For example, calling naturally has a bit of static to it. This would be a lot more preferred over a silky-smooth call that takes twice as long to work with.

## DDoS Attacks

When it comes to security, UDP's risks don't usually cause problems. A few packets loss usually does nothing. However, it can still be exploited for malicious purposes. Because UDP does not require a handshake, an attacker can send UDP datagrams to a server without needed a connection.

UDP's lack of security and integrity makes it usable by attackers for DDoS attacks. If an attacker is sending a magnitude of UDP packets to a target's ports, that target HAS to allocate resources to say that the port / feature is not reachable. If this is continuously happening, suddenly all the computer is doing is reacting to these false packets. Any legitimate traffic might not be responded to.




