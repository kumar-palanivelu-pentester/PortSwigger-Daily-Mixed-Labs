# Lab: 2FA simple bypass

**Category:** Authentication  
**Difficulty:** Apprentice

## Vulnerability

After correct username/password, the session is already valid. The 2FA step can be skipped by directly navigating to /my-account.

## Steps I Followed

1. Logged in as wiener and completed 2FA normally
2. Noted the /my-account URL
3. Logged in as carlos:montoya
4. When 2FA was requested, manually changed the URL to /my-account
5. Accessed Carlos account and solved the lab

## Why it worked

The application created a valid session after the first authentication factor and did not enforce 2FA before allowing access to the account page.

## Understanding

2FA must be enforced server-side before granting access to protected resources.
