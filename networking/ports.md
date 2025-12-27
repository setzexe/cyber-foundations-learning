# Ports

Ports are the numbered identifiers that tells a system which program of service should eceive incoming network data. If a house was the IP, each door in that house is a service on that IP. Ports identifies these services.

## Why Ports Exist

Multiple services can run on the same system. Ports allow services like web servers, SSH, databases, and mail services to all receive traffic simultaneously without conflict.

## Port Numbers 

Ports range from 0 - 65535. Common ranges include:

- 0 - 1023 --> Well known ports (Core services)
- 1024 - 49151 --> Registered ports (Includes custom services)
- 49152 - 65535 --> Ephemeral (Temporary client ports)

Servers typically listen on fixed ports. Clients use the ephemeral ports.

## Client Ports 

Client ports, or the emphemeral ports, are ports that temporarily exist for tasks or services that won't last a while. For example, if you load a tab in your browser to watch a youtube video, your computer tells youtube to send the youtube information to that room. This way, information about the youtube video is not being mixed up with other tabs.

# Listening vs Established Ports

Listening ports wait for incoming connections. These are the more common ones, where attacks happens. They could take bad / malicious data.

Listening ports become established ports once a connection is made. Note that this means ANY connection. Good or bad.

## Common Ports

These are very common ports you will experience and work with.

- 21 --> FTP. File Transfer Protocol. Moves files between computers.
    - Data is unencrypted. Anyone watching the transfer can see the data.
- 22 --> Secure Shell. A way for admins to log in remotely.
    - Much more secure than TelNet (23). Many attacked with brute force.
- 23 --> Telnet. Outdated version of SSH.
    - Data is sent as plain text. Very easily detectable. A MUST CLOSE.
- 25 --> SMTP. Email sending. Sends your email publicly.
    - Attackers can hijack this and send phishing / malicious emails.
- 53 --> DNS. Converts domains to IPs.
    - Hackers can poison this and redirect you to bad IPs.
- 80 --> HTTP. Unsecured web browsing.
    - This is old and outdated. Redirect to port 443.
- 443 --> HTTPS. Browsing with encryption.
    - Malicious requests = encryption bypassed and potential damage.
- 445 --> SMB. File sharing, sharing folders and printers.
    - Attacked OFTEN. Popular target for ransomware.

## Ports & Security

Open ports expose services and expand attack surface since they reveal running applications. Closed / filtered ports have way less exposure and are practically non-existent (very few exceptions) to hackers. So hackers have to map out and rely on these open ports.

Security often begins by controlling which ports are open. If you don't ned a port, do not open it. If you do, set proper precautions like firewalls. 

## Ports & Cybersecurity

A common mistake is assuming that because a port is open, it must be safe. No. Ports only provide access to a service, not security. This affects both normal people accessing these and people who with malicious intent. Authentication & Validation are still important.

Understanding ports is vital for understanding attack paths, analyzing traffic, interpretting scan results, identifying exposed results, etc. Ports connect networking to operating systems.



