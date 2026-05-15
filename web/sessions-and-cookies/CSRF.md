# CSRF (Cross-Site Request Forgery)

**Cross-Site Request Forgery** is an attack that occurs when a malicious site tricks a user into sending a request to a site where that user is trusted and authenticated. The browser automatically sends the user's session cookie, making the server believe it is a legitimate request.

CSRF tokens are what is used to prevent this. These are unique tokens that is tied to a user's session and embed's it into the client's web page. If any requests do not contain this CSRF token, the requests do not go through. It is like a code that only the client and server know. Outside sources can not see this under normal circumstances.

## How It Works

1. User logs into "bank.com" and receives a valid session cookie.
2. User visits "evil.com" (still authenticated to "bank.com").
3. "evil.com" contains a hidden code that triggers a request (img src="bank.com/transfer?amount=1000&to=attacker", for example.)
4. Browser automatically includes the session cookie in the request.
5. "bank.com" sees a valid session and processes the transfer.

The attacker never steals the session. They simply abuse the user's trust.

With a CSRF token, the request at step 3 would never be sent.

## Cybersecurity Context

- Browsers automatically include cookies in cross origin requests (by default).
- Servers trust authenticated sessions without verifying request origin.
- Users can't see or prevent the malicious request.

The impact of this includes account takeover, unauthorized transactions, state changes, data theft, etc.

## Defenses

- CSRF Tokens
    - Server generates a unique, unpredictable token. Attacker can't forge valid requests without it.
- SameSite Cookies 
    - Tells browser not to include cookies in cross-site requests. Strict is typically the one this works with, although LAX is a default.
- Origin Validation 
    - Server checks if request came from expected origin.

For the best defense, it is recommended to implement both SameSite headers & CSRF token.