# Day 1 - Lab 2: Username enumeration via different responses

**Category:** Authentication  
**Difficulty:** Apprentice

## Vulnerability

Login page returns different responses for invalid username vs valid username + wrong password.

## Steps I Followed

1. Captured login request
2. Used Burp Intruder with username wordlist
3. Identified valid username by different response length
4. Used the valid username and brute-forced password with wordlist
5. Found correct password by 302 status code
6. Logged in and solved the lab

## Why it worked

Different error messages allowed username enumeration. Once username was known, password brute-force became possible.

## Understanding

Always look for differences in:
- Response length
- Status code
- Error message text
