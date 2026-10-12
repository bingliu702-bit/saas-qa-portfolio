## SC-019: Check Console Errors During Page Load

**Test Website:** AcademyBugs

**Test Page:** Report Bugs

**Objective:** Check for Console errors and warnings during page loading and investigate their possible sources.

**Preconditions:**
- The AcademyBugs website is accessible.
- Google Chrome is available.
- Chrome DevTools can be opened.

**Test Data:** N/A

**Steps to Reproduce:**
1. Open the AcademyBugs Report Bugs page.
2. Press F12 to open Chrome DevTools.
3. Select the Console tab.
4. Clear existing Console messages.
5. Press Ctrl + R to refresh the page.
6. Check the Console for errors and warnings.
7. Use the Errors only and Warnings only filters to inspect the messages.
8. Hover over the source links to investigate the origin of the errors.
9. Capture screenshots of the Console results.

**Expected Result:**

The page should load and display its main content without unexpected Console errors related to website functionality.

**Actual Result:**

The page loaded and displayed its main content.

The Console displayed three resource-loading errors:
- Two Google Tag Manager requests failed with `ERR_SSL_PROTOCOL_ERROR`.
- One request to `cdn.polyfill.io` failed with `ERR_CONNECTION_CLOSED`.

Eight warnings were observed, including deprecated jQuery API usage and an EverBee AI extension warning.

During a separate Console inspection, a `TypeError` involving the `classList` property was traced to a script loaded from a `chrome-extension://` URL.

The network request failures have not been confirmed as website defects.

**Status:** Pending Investigation

**Evidence:**
- Console screenshot showing resource-loading errors.
- Console screenshot showing warnings.
- Screenshot showing the Chrome extension script URL.

**Notes:**

The error messages were investigated to distinguish website-related issues from browser extension activity. No website defect was confirmed from the Console messages alone.

---

## SC-020: Check Console Errors During Cart Quantity Adjustment

**Test Website:** AcademyBugs

**Test Page:** Shopping Cart

**Objective:** Verify whether increasing the product quantity generates new Console errors or warnings.

**Preconditions:**
- The shopping cart page is open.
- DNK Yellow Shoes is in the cart.
- The initial quantity is 2.
- Chrome DevTools is open on the Console tab.

**Test Data:**
- Product: DNK Yellow Shoes
- Initial quantity: 2
- New quantity: 3

**Steps to Reproduce:**
1. Open the shopping cart page.
2. Open Chrome DevTools and select the Console tab.
3. Clear existing Console messages.
4. Click the quantity increase (+) button once.
5. Observe the displayed quantity.
6. Check the Console for new errors and warnings.
7. Capture a screenshot without refreshing the page.

**Expected Result:**

The quantity should increase from 2 to 3 without generating unexpected Console errors related to the interaction.

**Actual Result:**

The displayed quantity increased from 2 to 3.

No new Console errors or warnings were observed after clicking the quantity increase button.

The item total and cart subtotal remained at $90.00. The Update button had not been clicked.

**Status:** Pass — Console observation only

**Evidence:**
- Screenshot showing quantity 3 and an empty Console message area.

**Notes:**

The test covered Console messages during the quantity adjustment, not the cart total recalculation.

The previously reported cart total issue is tracked separately in BR-001. No duplicate bug report was created.