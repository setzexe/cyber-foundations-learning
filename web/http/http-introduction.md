# Introduction to HTTP

HTTP (HyperText Transfer Protocol) is a rule set that defines how clients and servers communicate on the web. The process works like this:

- A client (browser, script, tool, etc) sends a request.
- A server sends back a response (Headers, HTML, images, etc)

HTTP defines how requests / responses are structured, what actions are being requested, and how success/failure is reported. Essentially, **HTTP is the language of the web.**

HTTP does not really work with security, like encryption or authentication. These are added on top of HTTP like through HTTPS, but these are not really part of HTTP itself.

## HTTP vs HTTPS (Brief)

- HTTP is the communication rules between server and client. Status codes, headers, methods, and beyond.
- HTTPS is HTTP in an encrypted tunnel. It is not just encrypted data, it's more of an encrypted passage way. This passage way is called **TLS (Transport Layer Security)**.

The HTTP data can still be mistrusted or exploitable if logic is flawed.

This will be elaborated on more in a markdown of its own.

## HTTP is Stateless

Each HTTP request is stateless, meaning it's independent. The server does not remember previous requests by default. This is fixed with stuff like cookies, tokens, or sessions. If these are misconfigured, a lot of vulnerabilities arise.

## Core HTTP Communication Model

Through HTTP, a client typically sends a *request* while a server sends back a *response*.

A **request** contains:
- Method (What you want to do)
- Path (What resource)
- Headers (Metadata, data about the data being sent)
- Optional body (Data being sent)

A **response** contains:
- A status code (result; did the request work?)
- Headers (Specific metadata)
- Optional body (Content or data)

This model is universal and is found from browsers to API's.

**HTTP Relevance in Cybersecurity**

Although HTTPS is everywhere, attackers can still:
- Send valid encrypted requests
- Abuse allowed HTTP behavior
- Manipulate inputs, headers, and parameters

Most web attacks are logic flaws or trust issues. Malicious headers could be sent that might respond with important information. HTTPS wouldn't know much better.

### HTTP is an Attack Surface

HTTP exposes endpoints, headers, methods, parameters, etc. Anything a server accepts via HTTP can be relayed, automated, modified, and repeated. You understand alot about a server by their HTTP responses.

Understanding HTTP lets you read traffic and understand vulnurabilities + logs/alerts.

If you can't read raw HTTP, you won't be able to fully understand web attacks. And you need to understand web atacks. The web grows more and more popular by the day.

