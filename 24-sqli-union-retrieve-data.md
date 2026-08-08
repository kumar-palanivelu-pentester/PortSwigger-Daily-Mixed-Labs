# Lab: SQL injection UNION attack, retrieving data from other tables

**Category:** SQL Injection  
**Difficulty:** Practitioner

## Vulnerability

UNION injection can be used to retrieve data from other tables (users) when column count and data types match.

## Steps I Followed

1. Confirmed 2 columns (both string-compatible) with `' UNION SELECT 'abc','def'--`
2. Extracted data: `' UNION SELECT username,password FROM users--`
3. Found administrator password in the response (view source)
4. Logged in as administrator and solved the lab

## Why it worked

UNION appended rows from the users table to the original query results. Both columns accepted string data, so usernames and passwords were returned in the page.

## Understanding

Full UNION attack flow: determine columns → find string columns → SELECT target data FROM other tables → use credentials.
