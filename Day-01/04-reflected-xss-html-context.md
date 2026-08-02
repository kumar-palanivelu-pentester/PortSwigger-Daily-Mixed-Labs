# Day 1 - Lab 4: Reflected XSS into HTML context with nothing encoded

**Category:** Cross-site Scripting (XSS)  
**Difficulty:** Apprentice

## Vulnerability

Search functionality reflects user input into the HTML page without any encoding.

## Steps I Followed

1. Entered the payload in the search box:
   ```html
   <script>alert(1)</script>
   ```
2. Clicked Search
3. Alert popup appeared → Lab solved

## Why it worked

The application did not encode or sanitize the input before reflecting it in the response. The browser executed the JavaScript.

## Understanding

This is the most basic form of Reflected XSS.
