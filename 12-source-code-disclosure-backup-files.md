# Lab: Source code disclosure via backup files

**Category:** Information Disclosure  
**Difficulty:** Apprentice

## Vulnerability

Backup files (.bak) containing source code are accessible in a hidden directory. Hard-coded database password is present in the source.

## Steps I Followed

1. Checked /robots.txt
2. Found /backup directory
3. Opened the .bak file
4. Found the hard-coded password and submitted it

## Why it worked

Developers left backup files on the server. robots.txt disclosed the path.

## Understanding

Always check robots.txt and common backup extensions (.bak, .old, .src, ~).
