# Day 17 - Decision Table Testing

## Test Objective

Verify order submission behavior under different combinations of login status, stock availability, and purchase permission.

## Business Rules (Simulated)

1. The user must be logged in to submit an order.
2. The product must be in stock.
3. The user must have purchase permission.
4. An order is accepted only when all three conditions are satisfied.

## Decision Table

| Rule | Logged In | In Stock | Permission | Expected Action |
|------|-----------|----------|------------|-----------------|
| R1 | Yes | Yes | Yes | Order accepted|
| R2 | Yes | Yes | No | Order rejected|
| R3 | Yes | No | Yes | Order rejected|
| R4 | Yes | No | No | Order rejected|
| R5 | No | Yes | Yes |Order rejected |
| R6 | No | Yes | No | Order rejected|
| R7 | No | No | Yes | Order rejected|
| R8 | No | No | No | Order rejected|

## Test Execution Summary

### Test Website
https://www.saucedemo.com/

### Verified Scenarios
- SC-029: Checkout with multiple products - Pass
- SC-030: Login rejection for a locked-out user - Pass

### Decision Table Execution
The eight decision table rules were designed using simulated business requirements.

The complete decision table was not executed because stock availability and purchase permission controls could not be verified on the test website.

### Bug Report
No confirmed bug was identified during these tests.
BR-010 was not created.