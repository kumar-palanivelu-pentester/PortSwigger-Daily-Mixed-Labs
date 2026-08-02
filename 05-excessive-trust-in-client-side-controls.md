# Lab: Excessive trust in client-side controls

**Category:** Business Logic  
**Difficulty:** Apprentice

## Vulnerability

The application trusts the price value sent from the client when adding items to the cart.

## Steps I Followed

1. Logged in as `wiener:peter`
2. Added the leather jacket to cart
3. Captured the `/cart` request in Burp
4. Changed the `price` parameter to a low value (1)
5. Refreshed the cart and placed the order
6. Lab solved

## Why it worked

Price validation was not properly enforced on the server side. The application accepted the client-supplied price.

## Understanding

Never trust any client-side data (price, quantity, discounts, roles, etc.). Always validate on the server.
