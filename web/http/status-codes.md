# Status Codes

HTTP Status Codes are codes (A set of 3 numbers) that are returned by the server. These indicate the result of a request. They tell the client whether the request succeeded, failed, needs redirection, or encountered an error.

You will see them in the HTTP responses on the top line:

    HTTP/1.1 200 OK
    (additional headers)

## Categories

### 1xx - Informational

- Request received
- Rarely used in practice nowadays

### 2xx - Success

The request was received and processed correctly. Common codes you may find include:

- 200 OK - request succeeded.
    - Does not indicate if the request was safe. The server simply accepted it.
- 201 Created - resouce successfully created.

### 3xx - Redirection

The client is told to go somewhere else. Common codes include:

- 301 Moved Permanently - Go to another web address.
- 302 Found - A redirection has found the correct server.

These are often abused in redirection attacks.

### 4xx - Client Errors

The request was invalid or not allowed. Common codes include:

- 400 Bad Request - Request might have been off.
- 401 Unauthorized - Authentication is required.
- 403 Forbidden - Forbidden. Possibly a user accessing an admin page.
- 404 Not Found - The resouce simply does not exist.

### 5xx - Server Errors

The server failed while processing a valid request. Common codes include:

- 500 Internal Server Error - The server itself might be faulty.
- 502 Bad Gateway - The middleman / gateway server failed to give a proper response.
- 503 Service Unavailable - The service is unavailble.

These can indicate crashs and are usually triggered by malformed or unexpected data.

## Cybersecurity Context

Status codes matter in relation to HTTP because they can expose server behavior and help identify vulnerabilities. They reveal valid endpoints, detect auth bypasses, and can map backend systems.

A response code will tell you *what* happened, not *why* something happened.


