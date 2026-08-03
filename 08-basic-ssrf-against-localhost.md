# Lab: Basic SSRF against the local server

**Category:** SSRF  
**Difficulty:** Apprentice

## Vulnerability

The stock check feature fetches a user-supplied URL on the server side. This can be abused to access internal resources.

## Steps I Followed

1. Captured the Check stock request
2. Changed `stockApi` to `http://localhost/admin`
3. Got the admin panel HTML in response
4. Changed it to `http://localhost/admin/delete?username=carlos`
5. Carlos was deleted and lab solved

## Why it worked

The server made a request to the URL I provided. Since it was internal (`localhost`), I could reach the admin interface.

## Understanding

Basic Server-Side Request Forgery. User-controlled URLs should never be fetched by the server without strict validation.
