# BR-002: Currency Selection Triggers a Crash Overlay and Fails to Convert Prices

## Summary

Selecting EUR, GBP, or JPY in the shopping cart triggers a temporary crash overlay. After the overlay disappears, the page becomes usable again, but the cart prices remain displayed in USD and are not converted to the selected currency.

## Environment

* **Test URL:** https://academybugs.com/my-cart/
* **Test date:** 2026-09-23
* **Browser:** Google Chrome 153.0.8010.53
* **Operating system:** Windows 11
* **Tester:** bingliu702-bit

## Preconditions

1. The AcademyBugs website is available.
2. A product has been added to the shopping cart.
3. The shopping cart page is open.
4. USD is the initially displayed currency.

## Test Data
## Evidence

### EUR Test

A screenshot shows that selecting EUR triggered the crash overlay and displayed the crash notification.

<img width="2048" height="987" alt="image" src="https://github.com/user-attachments/assets/b8ac123d-b42a-486e-bc3b-45c20ab37ae9" />

A second screenshot shows that, after recovery, EUR remained selected while the cart prices were still displayed in USD.

<img width="2048" height="1094" alt="image" src="https://github.com/user-attachments/assets/a2827917-4540-4b68-a069-0c4da88ddd65" />

### GBP Test

A screenshot shows that selecting GBP triggered the crash overlay and displayed the crash notification.

<img width="2048" height="1128" alt="image" src="https://github.com/user-attachments/assets/ea6fe17d-3bf3-47af-87a6-ebb46d2b0d80" />

A second screenshot shows that, after recovery, GBP remained selected while the cart prices were still displayed in USD.

<img width="2048" height="1010" alt="image" src="https://github.com/user-attachments/assets/f2e13723-f41f-4c82-b10b-507b4ceac42d" />

### JPY Test

A screenshot shows that selecting JPY triggered the crash overlay and displayed the crash notification.

<img width="2048" height="1178" alt="image" src="https://github.com/user-attachments/assets/a32bbf44-b352-457e-8809-99f8c29f9aba" />

A second screenshot shows that, after recovery, JPY remained selected while the cart prices were still displayed in USD.

<img width="2048" height="1054" alt="image" src="https://github.com/user-attachments/assets/4c14eb09-f0b3-4457-9ef9-6a676a477294" />

## Steps to Reproduce

1. Open the AcademyBugs shopping cart page.
2. Confirm that the cart prices are initially displayed in USD.
3. Open the **Select a Currency** drop-down list.
4. Select EUR, GBP, or JPY.
5. Observe the dark overlay and the displayed notification.
6. Wait at least 5 seconds for the overlay to disappear.
7. Observe the currency selector and the cart prices.
8. Repeat the test separately with each of the other currencies.

## Expected Result

The selected currency should be applied successfully.

The product price, cart subtotal, shipping fee, and grand total should be converted and displayed using the selected currency or its corresponding currency symbol.

The page should remain usable, and no crash notification or blocking overlay should be displayed.

## Actual Result

Selecting EUR, GBP, or JPY triggers a dark overlay and displays the following notification:

> You found a crash bug, examine the page for 5 seconds.

After approximately 5 seconds, the overlay disappears and the page becomes usable again.

The currency selector retains the selected currency, but the product price, cart subtotal, shipping fee, and grand total remain displayed in USD. The currency conversion does not complete successfully.

## Reproduction Rate

**3/3 tested currencies reproduced the issue (100%)**

| Tested currency | Crash overlay | Currency selector updated | Cart prices converted |
| --------------- | ------------: | ------------------------: | --------------------: |
| EUR             |           Yes |                       Yes |                    No |
| GBP             |           Yes |                       Yes |                    No |
| JPY             |           Yes |                       Yes |                    No |

## Recovery Behavior

The dark overlay disappears automatically after approximately 5 seconds, and the page becomes usable again without refreshing.

However, the selected currency is not applied to the cart prices.

## Severity

**Medium**

The issue temporarily blocks interaction with the page and prevents the currency conversion feature from working. However, the overlay disappears automatically, the page recovers without a refresh, and no data loss or permanent application failure was observed.

## Priority Recommendation

**High**

The issue affects all three tested alternative currencies in a customer-facing shopping cart. It should be investigated before the multi-currency feature is released or relied upon by international customers.

> Priority is a recommendation and should be confirmed by the product owner or project manager.

## Status

**Open**

## Evidence

### EUR Test

A screenshot shows that selecting EUR triggered the crash overlay and displayed the crash notification.

A second screenshot shows that, after recovery, EUR remained selected while the cart prices were still displayed in USD.

### GBP Test

A screenshot shows that selecting GBP triggered the crash overlay and displayed the crash notification.

A second screenshot shows that, after recovery, GBP remained selected while the cart prices were still displayed in USD.

### JPY Test

A screenshot shows that selecting JPY triggered the crash overlay and displayed the crash notification.

A second screenshot shows that, after recovery, JPY remained selected while the cart prices were still displayed in USD.

## Additional Notes

The issue was reproduced with every tested alternative currency. The temporary overlay behavior and the failed currency conversion were consistent across EUR, GBP, and JPY.
