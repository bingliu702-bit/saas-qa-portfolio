# Day 01 — Test Scenario Drafts

## SC-001: Verify Product List Display

### Test Objective

Verify that the product list is displayed correctly.

### Preconditions

The AcademyBugs website is accessible.

### Steps to Reproduce

1. Open the AcademyBugs website.
2. Navigate to the product list page.
3. Check the product images, names, prices, and action buttons.
4. Scroll down the page.

### Expected Result

- The product list page opens successfully.
- The main product information is clearly visible.
- There are no obvious overlapping, obstructed, or unusable elements.

### Actual Result

The product list page opens successfully.

In the same row, the product name, price, and **"Add to Cart"** button of the middle product, **"Dark Gray Jeans,"** are noticeably higher than those of the products on the left and right, **"DNK Yellow Shoes"** and **"Flamingo T-shirt."**

The three product cards are not vertically aligned.

### Execution

- **Attempts:** 2
- **Reproduction:** Reproduced in 2 out of 2 attempts (100%)
- **Test Result:** Fail

### Evidence

A screenshot of the product list page was saved as evidence.
<img width="744" height="341" alt="image" src="https://github.com/user-attachments/assets/63ef3262-9cda-47f4-b65c-c459c8f03a1e" />


## SC-002: Modify Product Quantity and Check Price

- **Test Objective:** Verify that the quantity can be modified and that the related price information is updated correctly.
- **Preconditions:** A product details page with an editable quantity field is open.
- **Test Data:** Increase the quantity from 1 to 3.

### Steps to Reproduce

1. Record the initial product price and quantity.
2. Click the **"+"** button to increase the quantity to 3.
3. Check the displayed quantity and price.

### Expected Result

- The quantity should be updated to 3.
- If the page displays a total price, the total should equal the unit price multiplied by 3.

### Actual Result

The initial quantity on the product details page is 1.

After clicking the **"+"** button, the quantity remains 1 and does not increase. Repeated clicks produce the same result.

After refreshing the page and repeating the test, the same result occurs.

When 3 is entered manually in the quantity field, the quantity is displayed as 3, but the page still shows a price of USD 45.00.

This price may represent the unit price. Whether the displayed price should be updated based on the quantity requires confirmation of the product requirements.

### Execution

- **Attempts:** 2
- **Reproduction:** The unresponsive **"+"** button was reproduced in 2 out of 2 attempts (100%).
- **Test Result:** Fail

### Evidence

A screenshot of the product details page was saved as evidence.

However, a static screenshot cannot fully demonstrate that the **"+"** button is unresponsive. A screen recording should be added to provide stronger evidence.
<img width="668" height="429" alt="image" src="https://github.com/user-attachments/assets/68d1c20b-ed1f-46cf-927a-a42af88e961a" />


## SC-003: Add a Specified Quantity of a Product to the Cart

### Test Objective

Verify that the selected product and specified quantity are correctly added to the shopping cart.

### Preconditions

- The product details page is open.
- The shopping cart functionality is available.

### Test Data

- Product: DNK Yellow Shoes
- Unit Price: $45.00
- Quantity: 2

### Test Steps

1. Open the product details page for DNK Yellow Shoes.
2. Set the product quantity to `2`.
3. Click **Add to cart**.
4. Open the shopping cart.
5. Verify the product name, unit price, quantity, subtotal, shipping fee, and Grand Total.

### Expected Result

- The correct product should be displayed in the shopping cart.
- The product quantity should be `2`.
- The unit price should match the product page.
- The subtotal should be calculated correctly based on the unit price and quantity.
- The Grand Total should be consistent with the values displayed on the cart page.

### Actual Result

- DNK Yellow Shoes was successfully added to the shopping cart with the correct product name, unit price, and quantity.
- The cart displayed:
  - Unit Price: $45.00
  - Quantity: 2
  - Subtotal: $90.00
  - Shipping: $7.99
  - Displayed Grand Total: $197.99
- Based on the values displayed on the cart page, the calculated total should be:

  `$90.00 + $7.99 = $97.99`

- However, the page displayed a Grand Total of `$197.99`, which was `$100.00` higher than the calculated total.
- The page was refreshed and the test was repeated. The same incorrect Grand Total was displayed again.
- Execution Count: 2
- Reproduction: 2 out of 2 attempts (100%)

### Status

**Fail**

### Evidence

A screenshot of the shopping cart page was saved as evidence, showing the `$90.00` subtotal, `$7.99` shipping fee, and the displayed Grand Total of `$197.99`.

<!-- Insert cart screenshot here -->
<img width="688" height="457" alt="image" src="https://github.com/user-attachments/assets/41ecef33-d2d4-4bcb-ab04-5660bd59b3bb" />


## SC-004: View and Modify Product Quantity in the Shopping Cart

### Test Objective

Verify that the shopping cart displays the current product quantity correctly and allows the quantity to be increased or decreased.

### Preconditions

- At least one product has been added to the shopping cart.
- DNK Yellow Shoes is displayed in the cart with an initial quantity of `2`.
- The unit price is `$45.00`.

### Test Data

- Product: DNK Yellow Shoes
- Unit Price: $45.00
- Initial Quantity: 2
- Increased Quantity: 3
- Decreased Quantity: 1
- Shipping: $7.99

### Test Steps

1. Open the shopping cart.
2. Verify the current quantity of DNK Yellow Shoes.
3. Click the `+` button to increase the quantity from `2` to `3`.
4. Observe the product Total, Cart Subtotal, and Grand Total.
5. Change the quantity from `2` to `1` using the `-` button.
6. Observe the product Total, Cart Subtotal, and Grand Total again.

### Expected Result

- The current product quantity should be clearly displayed.
- The `+` and `-` controls should update the quantity correctly.
- When the quantity changes, the product Total and Cart Subtotal should update consistently with the unit price and quantity.
- The Grand Total should be consistent with the values displayed on the cart page.

### Actual Result

#### 1. Increase Quantity

The initial quantity of DNK Yellow Shoes was `2`, with a unit price of `$45.00`.

After clicking the `+` button, the quantity successfully increased to `3`.

However, the product Total and Cart Subtotal remained at `$90.00` instead of updating to `$135.00`.

The page displayed:

- Quantity: 3
- Unit Price: $45.00
- Displayed Product Total: $90.00
- Calculated Product Total: $135.00
- Displayed Cart Subtotal: $90.00
- Shipping: $7.99
- Displayed Grand Total: $197.99

Based on the displayed shipping fee and the calculated subtotal for three items, the calculated total would be:

`$135.00 + $7.99 = $142.99`

The displayed Grand Total was `$197.99`.

#### 2. Decrease Quantity

After changing the quantity from `2` to `1`, the product Total and Cart Subtotal correctly updated to `$45.00`.

However, the Grand Total was displayed as `$152.99`.

The page displayed:

- Quantity: 1
- Unit Price: $45.00
- Product Total: $45.00
- Cart Subtotal: $45.00
- Shipping: $7.99
- Displayed Grand Total: $152.99

Based on the values displayed on the cart page, the calculated total would be:

`$45.00 + $7.99 = $52.99`

The displayed Grand Total was `$152.99`.

### Status

**Fail**

### Failure Summary

- After the quantity was increased to `3`, the product Total and Cart Subtotal did not update to reflect the new quantity.
- The displayed Grand Total was inconsistent with the subtotal and shipping values when the quantity was `3`.
- The displayed Grand Total was also inconsistent with the subtotal and shipping values when the quantity was `1`.

### Evidence

- Screenshot 1: Quantity `3`, Cart Subtotal `$90.00`, and Grand Total `$197.99`.
- Screenshot 2: Quantity `1`, Cart Subtotal `$45.00`, and Grand Total `$152.99`.

<!-- Insert Screenshot 1 here -->

<!-- Insert Screenshot 2 here -->
<img width="992" height="494" alt="image" src="https://github.com/user-attachments/assets/44c05dcd-43da-448f-8c35-7e9e5121fbee" />
<img width="932" height="571" alt="image" src="https://github.com/user-attachments/assets/2391b47c-4329-4b62-8594-d70403c8daf5" />


## SC-005: Switch Product Display Currency

### Test Objective

Verify that changing the selected currency updates the displayed currency and product price information consistently.

### Preconditions

- The shopping cart page is accessible.
- A currency selection feature is available.
- The initial displayed currency is USD.

### Test Data

- EUR
- GBP
- JPY

### Test Steps

1. Open the shopping cart page and note the current currency and displayed product price.
2. Select `EUR` from the currency selector.
3. Observe the page behavior, currency display, and product price.
4. Refresh the page and verify that the page becomes usable again.
5. Repeat the same test with `GBP`.
6. Repeat the same test with `JPY`.

### Expected Result

- The selected target currency should be applied according to the product's currency-switching behavior.
- The displayed currency symbol and product price should update consistently according to the product rules.
- The page should remain usable after the currency is changed.

### Actual Result

The initial currency displayed on the shopping cart page was USD.

When `EUR`, `GBP`, and `JPY` were selected individually, the same unexpected behavior occurred:

- A black overlay appeared on the page.
- The following message was displayed:

  `You found a crash bug, examine the page for 5 seconds.`

- While the overlay and message were displayed, the shopping cart page could not be used normally.
- The currency symbol and product price did not complete the expected update during this state.
- After the overlay/message disappeared or the page was refreshed, the page became usable again.
- After refreshing, the currency returned to USD.

### Execution Result

- Currencies tested: 3
- Test Data: EUR, GBP, JPY
- Reproduction: 3 out of 3 currency tests showed the same behavior (100%)

### Status

**Fail**

### Evidence

Screenshots were saved showing the behavior observed during the currency-switching tests.

- Screenshot 1: `EUR` selected with the black overlay and the message `You found a crash bug, examine the page for 5 seconds.`
- Screenshot 2: `GBP` selected with the same overlay/message.
- Screenshot 3: `JPY` selected with the same overlay/message.
- Additional screenshot(s): Page recovered after the overlay/message disappeared or after refresh.

<!-- Insert EUR screenshot here -->

<!-- Insert GBP screenshot here -->

<!-- Insert JPY screenshot here -->

<!-- Insert recovery screenshot here -->
<img width="1122" height="601" alt="image" src="https://github.com/user-attachments/assets/daec3ef7-f7c6-449b-840e-ff4b57a0660d" />

## Notes

## Execution Notes

## Test Execution Summary

All five test scenarios were executed, and the **Actual Result** and **Status** were recorded based on the observed behavior during testing.

A **Fail** status means that the actual result did not match the expected result. It does not automatically mean that a confirmed defect has been identified.

Any unexpected behavior should be evaluated against the product requirements, reproduction results, and supporting evidence before being confirmed as a defect. Confirmed defects will be documented separately in formal bug reports.

## Test Environment

- Operating System: Windows 11
- Browser: Google Chrome
- Browser Version: 153.0.8010.50
- Test Date: September 21, 2026
- Test Website: AcademyBugs
