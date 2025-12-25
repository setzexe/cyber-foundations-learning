# HTTP Requests & Responses

HTTP works on a request --> response mode. Clients send a request, server processes this requests, server returns a response.

## HTTP Requests (What the Client Sends)

A request tells the server what action to perform and on what resource.

    GET /login HTTP/1.1
    Host: example.com
    User-Agent: Mozilla/5.0

- Method: action to perform (GET in this example. Retrieves data)
- Path: Resource being accessed (/login)
- HTTP Version: 1.1
- Headers: Metadata about the request (User-Agent + Host)
- Body (optional): Data sent to the server (Moreso for Put. Not here)

## HTTP Response (What the Server Sends)

A response tells the client what happened and optionally returns data.

    HTTP/1.1 200 OK
    Content-Type: text/html
    Content-Length: 1234

    <html>...<html>

- The HTTP request went through. That 200 status codes mean the request went OK.
- The headers specify that HTML text with a length of 1234 is being sent back.
- The response also displays the html contents of the page.

## Headers

These are shared by requests and responses. These describe and control behavior, carry authentication data, and influence server decisions. Some examples include:

- Host
- Content-Type
- Authorization
- Cookies
- User-Agent

**Attackers will often modify eaders, inject unexpected values, and abuse trusted headers.**

## Bodies

Request Bodies, when they exist, can send data like form submissions, login credentials, or JSON payloads. Servers **MUST** validate body contents carefully. These can easily be messed with.

Reponse bodies, when they exist, can conatin HTML pages, JSON reponses, file data, and error messages. Sensitive information in responses can expose credentials or leak internal server logic, potentially allowing breaches.

## Stateless Interaction

As mentioned in the introduction, each pair of responses/requests are independant. The server does not memorize these by default. They rely on cookies, tokens, or sessions to track state.

___

**Security Failures happen when servers trust bad requests**

Understanding request/response flow is required to analyze traffic, understand web vulnurabilities, and detect malicious behaviors.


