# Lab: Basic SSRF against another back-end system

**Category:** SSRF  
**Difficulty:** Apprentice

## Vulnerability

Stock check feature can be used to scan internal IP range and access an admin interface on port 8080.

## Steps I Followed

1. Captured Check stock request
2. Used Burp Intruder to brute-force 192.168.0.1-255:8080/admin
3. Found the IP that returned 200
4. Changed path to /admin/delete?username=carlos
5. Lab solved

## Why it worked

The server fetched the user-supplied URL, allowing access to internal systems.

## Understanding

SSRF can be used for internal network scanning when the application fetches arbitrary URLs.
