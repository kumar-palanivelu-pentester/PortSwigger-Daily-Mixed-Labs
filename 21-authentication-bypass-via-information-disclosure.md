# Lab: Authentication bypass via information disclosure

**Category:** Information Disclosure + Authentication  
**Difficulty:** Apprentice

## Vulnerability

Admin panel is restricted to local IP. A custom header `X-Custom-IP-Authorization` is used to check the IP. The header name is disclosed via the TRACE method.

## Steps I Followed

1. Tried /admin and saw "only available to local users"
2. Changed request method to TRACE
3. Found header `X-Custom-IP-Authorization` in the response
4. Added header `X-Custom-IP-Authorization: 127.0.0.1`
5. Accessed /admin and deleted carlos

## Why it worked

TRACE method reflected the custom header. Spoofing the header with localhost IP bypassed the IP-based access control.

## Understanding

Custom headers used for access control can be discovered and spoofed. TRACE can leak such headers. Never rely solely on client-controlled headers for authorization.
