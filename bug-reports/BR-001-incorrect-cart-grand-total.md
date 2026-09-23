# BR-001: Incorrect Grand Total Displayed in Shopping Cart

## Summary

The shopping cart displays an incorrect grand total when the cart subtotal is USD 90.00 and the shipping fee is USD 7.99. The expected grand total is USD 97.99, but the page displays USD 197.99.

## Environment

* **Test URL:** https://academybugs.com/my-cart/
* **Test date:** 2026-09-23
* **Browser:** Google Chrome 153.0.8010.53
* **Operating system:** Windows 11
* **Tester:** bingliu702-bit

## Preconditions

1. The AcademyBugs website is available.
2. The product can be added to the shopping cart.
3. The shopping cart page can be opened normally.
4. USD is selected as the display currency.

## Steps to Reproduce

1. Open the AcademyBugs website.
2. Add the product priced at USD 45.00 to the shopping cart.
3. Open the shopping cart page.
4. Set the product quantity to `2`.
5. Click the **Update** button.
6. Confirm that the cart subtotal is USD 90.00.
7. Confirm that the shipping fee is USD 7.99.
8. Observe the displayed grand total.

## Expected Result

The grand total should equal the cart subtotal plus the shipping fee:

`USD 90.00 + USD 7.99 = USD 97.99`

Therefore, the page should display a grand total of **USD 97.99**.

## Actual Result

The page displays a grand total of **USD 197.99** instead of USD 97.99.

The displayed grand total is USD 100.00 higher than the expected total.

## Reproduction Rate

**1/1 attempt (100%)**

## Severity

**High**

The issue affects a core checkout calculation. An incorrect grand total may cause customers to be charged the wrong amount and may result in financial loss, abandoned purchases, or loss of customer trust.

## Priority Recommendation

**Urgent**

The issue should be investigated and fixed before the checkout flow is released or used for real transactions.

> Priority is a recommendation and should be confirmed by the product owner or project manager.

## Status

**Open**

## Evidence

<img width="1122" height="563" alt="image" src="https://github.com/user-attachments/assets/ae0a8d64-1a95-4422-a9e3-8421092cb331" />


The screenshot shows:

* Unit price: USD 45.00
* Quantity: 2
* Cart subtotal: USD 90.00
* Shipping fee: USD 7.99
* Displayed grand total: USD 197.99

## Additional Notes

The expected total was calculated from the values displayed in the cart summary. No tax or additional fee was displayed in the observed checkout summary.

