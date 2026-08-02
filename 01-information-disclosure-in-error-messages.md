# Lab: Information disclosure in error messages

**Category:** Information Disclosure  
**Difficulty:** Apprentice

## Vulnerability

Application shows verbose error messages (stack traces) that reveal the framework name and version.

## Steps I Followed

1. Opened a product page
2. Captured the request with `productId` parameter in Burp Repeater
3. Changed `productId` to a non-numeric value (string)
4. Triggered Internal Server Error
5. Found version `Apache Struts 2 2.3.31` in the response
6. Submitted the version and solved the lab

## Why it worked

The application did not handle unexpected input properly and leaked sensitive technical information in the error response.

## Understanding

Always test how the application behaves with invalid data types. Error messages can reveal useful information for further attacks.
