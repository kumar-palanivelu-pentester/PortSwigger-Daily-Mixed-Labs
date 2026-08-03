# Lab: File path traversal, simple case

**Category:** Path Traversal  
**Difficulty:** Apprentice

## Vulnerability

Product image loading is vulnerable to path traversal. User-controlled filename is used to read files from the server.

## Steps I Followed

1. Intercepted a product image request
2. Changed the filename parameter to `../../../etc/passwd`
3. Response contained the contents of `/etc/passwd`
4. Lab solved

## Why it worked

The application did not sanitize `../` sequences, allowing traversal outside the intended directory.

## Understanding

Classic directory traversal. Always test file-related parameters with `../` sequences.
