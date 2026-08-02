# Lab: SQL injection vulnerability in WHERE clause allowing retrieval of hidden data

**Category:** SQL Injection  
**Difficulty:** Apprentice

## Vulnerability

Product category filter is vulnerable to SQL injection. The query includes `AND released = 1` which hides unreleased products.

## Steps I Followed

1. Selected a category
2. Captured the request in Burp Repeater
3. Injected payload: `' OR 1=1--`
4. Unreleased products appeared in the response
5. Lab solved

## Why it worked

Original query:
```sql
WHERE category = 'Lifestyle' AND released = 1
```

After injection:
```sql
WHERE category = 'Lifestyle' OR 1=1--' AND released = 1
```

`OR 1=1` made the condition always true and `--` commented out the rest.

## Understanding

Basic boolean-based SQL injection to bypass filter conditions.
