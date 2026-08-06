# Lab: Password reset broken logic

**Category:** Authentication  
**Difficulty:** Apprentice

## Vulnerability

The password reset confirmation step does not properly validate the reset token. Changing the username parameter allows resetting another user's password.

## Steps I Followed

1. Requested password reset for my account (wiener)
2. Completed the reset flow and captured the final request
3. Removed the token and changed username to carlos
4. Set a new password and logged in as carlos

## Why it worked

The final password change request did not validate the reset token properly. Only the username parameter was used.

## Understanding

Every step of a multi-step process must independently verify authorization and tokens.
