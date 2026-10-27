# Day 19 - Exploratory Testing Session Report

## 1. Session Information

- Test Website: AcademyBugs.com
- Test Date: 2026-10-27
- Operating System: Windows 11
- Browser: Google Chrome
- Testing Method: Exploratory Testing
- Planned Duration: 90 minutes
- Actual Duration: Approximately 45 minutes

## 2. Session Objective

Explore shopping cart and checkout-related features to identify unexpected behavior in price calculations, coupon validation, and gift card validation.

## 3. Test Coverage

The following areas were explored:

- Shopping cart quantity and price calculations
- Checkout page observations
- Empty and invalid coupon validation
- Empty and invalid gift card validation
- Login page language consistency

## 4. Test Execution Summary

### Shopping Cart

- Blue Hoodie unit price: $111.00
- Quantity: 2
- Cart Subtotal: $222.00
- Grand Total: $322.00
- An unexplained difference of $100.00 was observed.

A similar issue had been reported previously.

### Coupon Validation

- Empty and invalid coupon inputs were tested.
- Both displayed "Not a valid coupon code".
- Cart totals remained unchanged.
- No new defect was confirmed.

### Gift Card Validation

- Empty and invalid gift card inputs were tested.
- Both displayed "Not a valid gift card number".
- Cart totals remained unchanged.
- No new defect was confirmed.

### Checkout and Login Observations

- The unexplained cart total difference was also observed on the checkout page.
- A previously reported language inconsistency was observed again.

## 5. Defect Summary

- New confirmed defects: 0
- New bug reports created: 0
- Previously observed issues encountered again: 2

The previously observed issues involved cart total calculations and language consistency.

No duplicate bug reports were created.

## 6. Time Management

- Planned testing time: 90 minutes
- Actual testing time: Approximately 45 minutes
- Main activities: Investigating unexpected behavior, retesting, and capturing screenshots.

A detailed minute-by-minute timeline was not recorded.

## 7. Areas Not Covered

- Successful coupon redemption
- Successful gift card redemption
- Completed payment transactions
- Order fulfillment
- Performance testing
- Security testing

## 8. Session Assessment

No new defects were confirmed during this exploratory testing session.

Previously observed issues were encountered again.

The session provided additional observations about shopping cart calculations, coupon validation, and gift card validation.

The absence of newly confirmed defects does not mean that all tested features are defect-free.

## 9. Recommended Follow-up

- Review the existing cart total bug report.
- Confirm the expected calculation rules for additional charges.
- Review the previously reported language inconsistency.
- Test successful coupon and gift card redemption when valid test data becomes available.
- Improve time tracking during future exploratory testing sessions.