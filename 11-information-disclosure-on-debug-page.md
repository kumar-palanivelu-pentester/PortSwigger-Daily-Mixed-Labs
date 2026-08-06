# Lab: Information disclosure on debug page

**Category:** Information Disclosure  
**Difficulty:** Apprentice

## Vulnerability

A debug page is publicly accessible and discloses sensitive environment variables including SECRET_KEY.

## Steps I Followed

1. Used feroxbuster to discover directories
2. Found the debug page
3. Extracted the SECRET_KEY value
4. Submitted it to solve the lab

## Why it worked

The application left a debug/phpinfo style page accessible without authentication. Environment variables were exposed.

## Understanding

Debug pages and phpinfo should never be accessible in production.
