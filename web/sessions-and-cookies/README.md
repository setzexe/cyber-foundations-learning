# Sessions & Cookies

Sessions and cookies are mechanisms that allow servers to recognize & remember clients across multiple requests. Making user's do things like signing in or entering info every time they want to use a site is annoying. HTTP itself is stateless, meaning it does not remember it's past state. **Sessions and cookies** create this "state" (memory) ability. These allow authentication, tracking, and personalization. 

In cybersecurity, these are a critical attack surface. Misconfigured cookies can lead to session hijacking, fixation, and privilege escalation.

## Cookies

Cookies are small files that are stored on the client (browser) and sent with every HTTP request to a specific domain. These help the server know about prior important client information, like passwords or even ad traffic. Servers use *set-cookie* headers to assign them

### Cookie Strutucre

DO STUFF HERE

- Name = The identifier
- Value = Data
- Domain = Which site can access these cookies
- Path = Which urls exist on that domain
- Expiration - When it expires (Can be session or permanent)
- Secure Flag - Specifies if it is only sent over HTTPS
- HttpOnly Flag - Inaccessible to JavaScript (Prevents XSS theft)
- SameSite Flag - Prevents CSRF Attacks
    - Strict - Cookie is only sent in a request IF it comes from the same site that created it. Bank portals for example.
    - LAX - The default. This allows cookies to be sent if the user clicks a link. Only GETS are sent, POST are not.
    - None - All cookies are sent. This includes POSTS like payment information, which makes it risky. To allow this, cookies MUST be sent via HTTPS.

### Key Security Attributes

- The HttpOnly flag prevents JavaScript from reading cookies. This blocks XSS / injection based session theft. 
- Secure cookies travel only through HTTPS. Note that HTTPS is usually the web default.

### Other notes

- These are the reason you often do not need to log in to a site everytime; the cookie remembers. Same with internet shopping carts.
- These are also what gives you personalized ads.

## Sessions

A session is a server-side state tied to a client. It works directly with cookies to keep you logged in. The server will create a unique "Session ID" that is sent to your browser. This session ID is stored as a cookie. On subsequent requests, the client sends the session ID, and the server retrieves the associated data.

### Session Flow

- Client logs in, or session creation is triggered
- Server creates session ID and stores session data
- Server sends session ID to client (via Set-Cookie header)
- Client includes this session ID in future requests
- Server validates ID & retrieves session data

### Common Vulnerabilities

- Session Fixation
    - Attackers force a known session ID onto a victim. If a victim uses this, attackers can exploit any access that the victim has.
- Session Hijacking
    - Attackers can steal a valid session ID (XSS, sniffing, etc) and impersonate the victim.
- Weak Session ID's
    - Predictable / short ID's = brute force more possible.
- Cookie Theft
    - XSS injection, malware / malicious scripts, man-in-the-middle attacks, etc.
- CSRF
    - Attacker tricks a victim into making a request that modify's the server state via a victim's valid session.
- Missing HttpOnly / Secure flags 
    - Makes cookies vulnerable to network interception or XSS via JavaScript.

## Differences Between Cookies & Sessions

Cookies are stored via the client-side, store a limited amount of data (4KB usually) and can persist for a long time.

Sessions are server-side and usually end when the browser is closed. Due to this, and the fact that information is stored via server security, the information is a lot less at risk.

