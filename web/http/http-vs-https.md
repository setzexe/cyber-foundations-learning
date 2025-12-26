# HTTP vs HTTPS

Although discussed in the introduction, this markdown details more specific information on the difference between HTTP and HTTPS.

HTTP (HyperText Transfer Protocol) defines how web data is structured and exchanged between clients and servers. It specifies requests, responses, methods, headers, and status-codes, but dos not provide the security itself.

HTTPS (HyperText Transfer Protocol Secure) is HTTP wrapped inside encryption (TLS, or Transport Layer Security). It protects all the data and content in transit. It does NOT affect HTTP or change how it works.

## Core Difference

- HTTP = Communication Rules.
- HTTPS = Encrypted Communcation Travel

HTTP data would still be processed and trusted/mistrusted without the use of HTTPS.

If HTTP is a car holding data, HTTPS is a bordered highway protecting that data.

## What HTTPS Protects Against

- Packet Sniffing
- Man-in-the-middle attacks
- Credential Interception

This matters heavily on public Wi-Fi and untrusted networks.

## What HTTPS Does NOT Protect Against

HTTPS does not prevent the following:

- Malicious Input 
- SQL Injection
- XSS
- Broken / Misconfigured Authentication
- Logic Flaws
- Priviledge Escalation

If a server accepts a request, even if it is malicious, HTTPS will still deliver it.

## Security Reality

Although HTTPS ensures secrecy and integrity, security failures often happen after decryption and inside application logic, possibly due to bad validation.

Modern attacks send well-formed HTTP requests that look like legit requests, but may hold improper and malicious scripts or injections. Attackers do not try to break encryption, they exploit trust and assumptions.