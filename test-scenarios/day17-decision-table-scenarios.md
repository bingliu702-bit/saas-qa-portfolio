# Day 17 - Test Scenarios

## SC-029: Verify Checkout with Multiple Products

**Test Website:** https://www.saucedemo.com/

**Test Account:** standard_user

**Scenario:** Verify that a logged-in user can successfully complete checkout with multiple products.

### Steps

1. Open the SauceDemo website.
2. Log in with username "standard_user" and password "secret_sauce".
3. Add the following products to the cart:
   - Sauce Labs Backpack
   - Sauce Labs Bike Light
   - Sauce Labs Fleece Jacket
4. Open the shopping cart.
5. Click Checkout.
6. Enter the required checkout information.
7. Click Continue.
8. Review the order summary.
9. Click Finish.

### Expected Result

The order should be submitted successfully, and an order confirmation page should be displayed.

### Actual Result

The "Checkout: Complete!" page was displayed with the message "Thank you for your order!"

### Status

Pass

## SC-030: Verify Login Rejection for a Locked-Out User

**Test Website:** https://www.saucedemo.com/

**Test Account:** locked_out_user

**Scenario:** Verify that a locked-out user cannot log in with the correct password.

### Steps

1. Open the SauceDemo website.
2. Enter the username "locked_out_user".
3. Enter the password "secret_sauce".
4. Click the Login button.

### Expected Result

The system should reject the login attempt because the account is locked.

### Actual Result

The system rejected the login attempt and displayed the error message:
"Epic sadface: Sorry, this user has been locked out."

### Status

Pass