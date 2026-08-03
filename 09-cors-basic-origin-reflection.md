# Lab: CORS vulnerability with basic origin reflection

**Category:** CORS  
**Difficulty:** Apprentice

## Vulnerability

The application reflects any Origin header in the `Access-Control-Allow-Origin` response header and allows credentials.

## Steps I Followed

1. Logged in and captured `/accountDetails` request
2. Added `Origin: https://example.com` and confirmed it was reflected
3. Created an exploit on the exploit server using XMLHttpRequest with `withCredentials = true`
4. Delivered the exploit to the victim
5. Retrieved the administrator API key from the log and submitted it

## Why it worked

The server trusted any Origin and allowed credentialed cross-origin requests. This allowed stealing authenticated data from another origin.

## Understanding

Never reflect Origin headers without a strict allowlist. Especially dangerous when combined with `Access-Control-Allow-Credentials: true`.
