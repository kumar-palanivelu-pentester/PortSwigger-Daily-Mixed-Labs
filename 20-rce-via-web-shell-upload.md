# Lab: Remote code execution via web shell upload

**Category:** File Upload  
**Difficulty:** Apprentice

## Vulnerability

Avatar upload functionality performs no validation on file type. PHP files can be uploaded and executed.

## Steps I Followed

1. Logged in as wiener:peter
2. Uploaded a PHP web shell: `<?php echo file_get_contents('/home/carlos/secret'); ?>`
3. Accessed `/files/avatars/shell.php`
4. Retrieved the secret and submitted it

## Why it worked

No file type or content validation. The server executed the uploaded PHP file, allowing arbitrary code execution and file read.

## Understanding

Unrestricted file upload leading to RCE is a critical vulnerability. Always validate file type, content, and store uploads outside the web root when possible.
