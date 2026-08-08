# Lab: SQL injection UNION attack, finding a column containing text

**Category:** SQL Injection  
**Difficulty:** Practitioner

## Vulnerability

After knowing the column count (3), identify which column accepts string data so that text (usernames, passwords) can be extracted later.

## Steps I Followed

1. Confirmed 3 columns with NULL,NULL,NULL
2. Replaced each NULL one by one with the lab-provided random string
3. Position 2 accepted the string: `' UNION SELECT NULL,'YOUR-STRING',NULL--`
4. Lab solved

## Why it worked

Only columns with a compatible data type (string/text) will accept string values. Other positions caused errors.

## Understanding

Finding string-compatible columns is required before extracting useful text data with UNION.
