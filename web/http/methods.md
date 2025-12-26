# HTTP Methods

HTTP methods define what action the client wants a server to perform on a resource. They tell the server what kind of operation is being requested, and how that request should be handled. Servers should handle and restrict methods carefully. Bad handling = potential leak of information that servers do not want to leak.

## Core Methods (The Essentials)

### GET

Retrieves data from a server. These should NOT change server state. When you load a website, it utilizes GET. 

GET requests are super easy to replay. Sensitive data in URLs can leak. 

    GET /profile HTTP/1.1
    Host: example.com
    User-Agent: Mozilla/5.0

Request wants to GET the profile page (utilizing HTTP 1.1)from the example.com host, from Mozilla 5.0.

### POST

Sends data to the server. Commonly used to create or submit data. You will find this often in logins and form submissions.

These are where most injection attacks occur. Servers must validate these inputs very carefully.

    POST /login HTTP/1.1
    Host: example.com
    Content-Type: application/x-www-form-urlencoded
    Content-Length: 32


    username=setz&password=1357

Post the cooresponding user & pass into the login page in example.com.

### PUT

Replaces / updates an existing resource. Used commonly for updating records (credentials) or modifying stored data.

This is often blocked or restricted. It is HEAVILY dangerous if exposed without authorization because you could potentially edit critical server information.

    PUT /users/123 HTTP/1.1
    Host: example.com
    Content-Type: application/json
    Content-Length: 45

    {"email":"newemail@example.com"}

    Update user 123 with the new email.

### DELETE

Removes a resource from a server. Commonly used for deleting accounts or data.

EXTREMELY sensitive. Same as put or post, this requires careful validation. 

    DELETE /users/123 HTTP/1.1
    Host: example.com
    Authorization: Bearer token123

Requesting to delete user 123.

### HEAD

Same as GET, except only headers are returned. No response body. Good for verifying if a resource exists, or just for general recon and monitoring. This is common in recon tools as it can reveal server behavior without fetching content. 

    HEAD /admin HTTP/1.1
    Host: example.com

No response body, just getting example's admin page headers.

## Cybersecurity Context

HTTP methods control server behavior and can expose functionality. Misconfigured methods (successfully using a DELETE on a GET) can lead to data manipulation, unauthorized actions, etc.