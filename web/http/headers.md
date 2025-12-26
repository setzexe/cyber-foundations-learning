# HTTP Headers

HTTP Headers are key-value pairs that provide metadata about a request / response. These tell a server how to process the message, who is sending it, what type of data is included, etc. These directly affect server behavior.

## Request Headers (Client --> Server)

These headers describe the client + the request. Common request headers include:

- Host - Specifies the target domain, and is required in HTTP/1.1 (the most common HTTP). Host manipulation can lead to routing issues.
- User-Agent - Identifies the client software. Browsers, scripts, and tools all set this. These are often logged and can be spoofed.
- Content-Type - Describes the format of the request body. JSON, urlencoded form, etc. Mismatched types can bypass validation. 
- Content-Length - Size of the request body in bytes. Incorrect handling can cause parsing issues.
- Authorization - Carries authentication credentials like basic auth or tokens. This is **critical**. Improper validation = auth bypass.
- Cookie - Sends stored session data to a server as a way of memory management. Misconfigured cookies could lead to priviledge escalation or session hijacking.

## Response Headers (Server --> Client)

These headers describe the response and how it is handled. Common response headers include:

- Set-Cookie - Assigns cookies to the client. Used for tracking, sessions, and memory management. Misconfigured cookies allow for session theft or malicious script injection.
- Content-Type - Describes response body format. Incorrect types can enable XSS (The injection of scripts into websites). 
- Content-Length - The size of the response body.

## Cybersecurity Context

Headers control authentication, manage sessions, influence server logic and affect client behavior. They give extra information both to the server and client for more proper responses. Attackers will often modify headers and inject unexpected values to get malicious results. 

Headers are trusted heavily by the servers. They expect the client to behave correctly. Often times, this just leads to abuse.





