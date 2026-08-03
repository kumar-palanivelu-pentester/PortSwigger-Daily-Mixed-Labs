# Lab: CSRF vulnerability with no defenses

**Category:** CSRF  
**Difficulty:** Apprentice

## Vulnerability

The email change functionality has no CSRF protection (no token, no SameSite restrictions, etc.).

## Steps I Followed

1. Logged in and captured the change email request
2. Created a simple HTML form PoC that auto-submits the email change
3. Hosted it on the exploit server
4. Delivered the exploit to the victim
5. Victim’s email was changed and lab solved

## Why it worked

There was no anti-CSRF token or other defense. Any site could make the victim’s browser send the email change request while they were logged in.

## Understanding

State-changing requests (POST) must be protected with CSRF tokens or SameSite cookies.
