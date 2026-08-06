# Lab: DOM XSS in document.write sink using source location.search

**Category:** DOM-based XSS  
**Difficulty:** Apprentice

## Vulnerability

JavaScript uses document.write with data from location.search without proper encoding.

## Steps I Followed

1. Tested search functionality
2. Observed input reflected inside an attribute via document.write
3. Used a payload to break out and execute alert
4. Lab solved

## Why it worked

User-controlled data from the URL was written into the DOM using document.write without sanitization.

## Understanding

DOM XSS occurs entirely on the client side. Always check JavaScript sinks like document.write, innerHTML, etc.
