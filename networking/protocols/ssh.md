# SSH

SSH (Secure Shell Protocol) is the protocol that is used to send commands to a server over an unsecured network. This protocol encrypts connection between devices. This makes it commonly used for remote admin control, managing infrastructure, and transferring files. Administrators can handle servers and devices from afar. This is in port 22.

SSH creates a connection between a user's client and a faraway device/server. This connection is encrypted in a way so that anyone trying to intercept this would only see static. 

The old option used to be port 23, Telnet. This did not encrypt at all though, everything could be seen as plaintext. Obviously, if you end up on a compromised internet or network, anyone can read these requests and get whatever information you are putting down. 

Linux & Mac already have SSH. Windows might require an SSH service.

## Tunneling / Port Forwarding

Tunneling is the process of sending packets through a protocol or path they would typically not use. In the case of SSH, one device might send data to a 2nd client / device first before sending it to the main recipient device.

Let's say you had a private network, but wanted to get data to your main rig without immediate outside interferance. Instead of just sending it from the remote client to the main rig, you can send the data to a client that takes internet traffic or data in general. This device from the private network can then send the data to the main rig. The information is forwarded from this secondary device via the SSH port. 

## TCP/IP 

SSH runs atop the TCP/IP suite. Because a connection is needed and information needs to be exact, TCP is best here.

# Cryptography

SSH uses the public key cryptography method to encrypt and decrypt data. There is a public and private key-- no one besides those in the connection should have the private key. Both sides of the connection authenticate each other using these keys.

It is worth noting that even with this secured encryption, the user using SSH will probably need to verify something like a username or password.

## Cybersecurity Relevance

SSH handles things like file transfer, tunneling, remote authentication & configuration, cryptography, replacing insecure ports (telnet...), etc. It has a lot of security based on it's cryptography. 

This is a double edged sword. Attackers would LOVE to attack this because of how much it can do. If an attacker gains access to these RSA keys to break the crpytography, attackers can now do what admins do and potentially destroy the entire network.