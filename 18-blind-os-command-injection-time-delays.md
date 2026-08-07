# Lab: Blind OS command injection with time delays

**Category:** OS Command Injection  
**Difficulty:** Practitioner

## Vulnerability

Feedback form is vulnerable to blind OS command injection. Command output is not returned, but time delays can be used to confirm execution.

## Steps I Followed

1. Submitted feedback form and captured the request
2. Injected time delay payload in the email parameter: `x||ping -c 10 127.0.0.1||`
3. Observed ~10 second delay in the response
4. Lab solved

## Why it worked

User input was passed to a shell command without sanitization. Using `ping -c 10` caused a measurable delay, confirming command execution.

## Understanding

Blind command injection is detected using time-based techniques when output is not reflected.
