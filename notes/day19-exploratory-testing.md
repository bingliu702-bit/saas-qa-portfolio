# Day 19 - Exploratory Testing Notes

## 1. Test Information

- Website: AcademyBugs.com
- Operating System: Windows 11
- Browser: Google Chrome
- Testing Method: Exploratory Testing
- Test Date: 2026-10-27

## 2. Shopping Cart Exploration

### Test Actions

1. Added Blue Hoodie to the shopping cart.
2. Observed the cart total with quantity 1.
3. Increased the quantity to 2.
4. Checked the subtotal and grand total.
5. Continued to the checkout page.

### Observations

- Product price: $111.00
- Quantity: 2
- Cart Subtotal: $222.00
- Grand Total: $322.00
- An unexplained difference of $100.00 was displayed.
- The difference was also observed on the checkout page.

### Assessment

A similar cart total issue had been reported previously.

This observation should be checked against the existing bug report before creating a new defect.

## 3. Coupon Validation Exploration

### Test Actions

1. Submitted an empty coupon field.
2. Entered INVALID123.
3. Clicked APPLY COUPON.
4. Observed the error message and cart totals.

### Observations

- Both inputs displayed "Not a valid coupon code".
- The invalid code remained in the input field.
- Cart Subtotal remained $222.00.
- Grand Total remained $322.00.

### Assessment

The invalid coupon was rejected.

The website's detailed validation requirements are unknown.

No new defect was confirmed.

## 4. Gift Card Validation Exploration

### Test Actions

1. Submitted an empty gift card field.
2. Entered INVALID123.
3. Clicked REDEEM GIFT CARD.
4. Observed the error message and cart totals.

### Observations

- Both inputs displayed "Not a valid gift card number".
- The invalid code remained in the input field.
- Cart Subtotal remained $222.00.
- Grand Total remained $322.00.

### Assessment

The invalid gift card was rejected.

The website's detailed validation requirements are unknown.

No new defect was confirmed.

## 5. Checkout Page Observation

### Observations

- The checkout page displayed billing information fields.
- The cart subtotal was $222.00.
- The grand total was $322.00.
- A previously observed language inconsistency was encountered on the login page.

### Assessment

The language inconsistency had been reported previously.

No new bug report was created for this observation.

## 6. Session Findings

- Existing cart total issue observed again.
- Existing language inconsistency observed again.
- Coupon validation explored.
- Gift card validation explored.
- No new defect confirmed during this session.

## 7. Areas Not Covered

- Successful coupon redemption
- Successful gift card redemption
- Completed payment transactions
- Order fulfillment
- Performance and security testing