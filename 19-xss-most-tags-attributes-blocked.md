# Lab: Reflected XSS into HTML context with most tags and attributes blocked

**Category:** XSS  
**Difficulty:** Practitioner

## Vulnerability

WAF blocks most common XSS tags and attributes. Allowed tags and events must be enumerated to bypass the filter.

## Steps I Followed

1. Confirmed common payloads were blocked
2. Used Burp Intruder to find allowed tags (body, math)
3. Used Intruder again to find allowed events (ononline, onoffline, onresize)
4. Crafted payload with body + onresize
5. Used exploit server with iframe to trigger print() without user interaction
6. Lab solved

## Why it worked

WAF used a blacklist. By enumerating allowed tags and events, a working payload was built. iframe onload forced a resize to trigger the event.

## Understanding

When most tags are blocked, systematically test which tags and event handlers are permitted.
