# Lab: OS command injection, simple case

**Category:** OS Command Injection  
**Difficulty:** Apprentice

## Vulnerability

The product stock checker executes a shell command using user-supplied input and returns the raw output.

## Steps I Followed

1. Opened a product and clicked Check stock
2. Captured the request in Burp
3. Injected payload in `storeId` parameter (e.g. `1|whoami`)
4. Response showed the current username
5. Lab solved

## Why it worked

User input was directly used in an OS command without sanitization. Special characters like `|` allowed command chaining.

## Understanding

Basic OS command injection. Always test parameters that interact with system commands.
