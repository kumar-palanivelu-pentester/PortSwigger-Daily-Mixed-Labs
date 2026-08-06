# Lab: SQL injection vulnerability allowing login bypass

**Category:** SQL Injection  
**Difficulty:** Apprentice

## Vulnerability

Login form is vulnerable to SQL injection. Using a comment sequence bypasses the password check.

## Steps I Followed

1. Entered username: administrator'--
2. Entered any password (test)
3. Logged in as administrator

## Why it worked

```sql
WHERE username = 'administrator'--' AND password = 'test'
```

The `--` commented out the password check.

## Understanding

Classic authentication bypass using SQL injection.
