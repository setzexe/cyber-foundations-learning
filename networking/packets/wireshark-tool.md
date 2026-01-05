# Wireshark

Wireshark is a very common tool when it comes to understanding packets. It is a network packet analyzer. Blue team benefits alot from wireshark as it allows the understanding incoming packets.

Unencrypted data is readable. But even if the data comes unencrypted, you will still get the ability to see who sent it, where it came from, what it is trying to do, etc.

## How To Use

1. Pick your Interface

- When you open Wireshark, you'll see a list of interfaces like Wi-Fi, Ethernet, Bluetooth, etc. Click the one you want, which is usually the one with a pulsing line like a heartrate monitor. Double click that to start "sniffing" data.

2. Start/Stop

- Packets start showing once you open the interface. The top left holds a red square and a blue shark fin. Red square to stop, blue shark fin to start over.

3. Display Filters

- You obviously do not need every packet ever. This is where the search bar comes in. You can put in filters to find packets that you specifically are looking for.

## Layout

Wireshark follows a three-pane layout. 

- The top box shows your packet summary (source, port, protocol, etc). 
- The bottom left box shows the specific details of the packet. 
- The bottom right box shows the raw data + ASCII. 

Packets appear in the top box and can often have different colors. Most colors just coorespond with types of traffic or protocols. However, there are some to watch out for. You might see *black* alot, which can indicate packet loss or error.

## Common Filters

These are commonly used filters that can sniff out reliable packets.

- ip.addr == 192.168.1.1 --> See everything involving a specific device.
- HTTP / DNS --> Any protocol works, but this lets you only see packets via that protocol.
- tcp.flags.syn == 1 --> Find the start of new connections.
- frame contains "password" --> Finds unencrypted credentials.

If you want to follow a stream or "conversation" via a certain protocol, simply right click a packet > follow > TCP (or whatever protocol) stream. Now these packets can be seen as a "readable" conversation.

## Two Exercises

To understand a bit more on how Wireshark works, or the utility of Wireshark, we will do two very simple activities.

### Ping Test

Open Wireshark and open your Wi-Fi (or Ethernet, whichever is active). Apply the *icmp* filter to only get ping packets. 

Go to your termial and ping 8.8.8.8. 

You will see these ping packets show up on Wireshark.

### Packet Anaylsis

Go to your interface with the most activity (usually Wi-Fi). 

Go to your browser and go to any website *that you trust.* Youtube, Pinterest, etc.

Stop the Wireshark capture and look up your *HTTP* packets.

If you loaded into your wanted webpage correctly, you should see some HTTP packets load up with a request like GET / HTTP/1.1 and a response like HTTP1.1 200 OK.

You can go to the bottom right panel to actually view the HTTP request itself.