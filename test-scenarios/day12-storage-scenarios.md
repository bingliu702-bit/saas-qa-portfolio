# Day 12 — Browser Storage Test Scenarios

## Test Environment

- Operating System: Windows 11
- Browser: Google Chrome
- Test Date: October 13, 2026
- Tool: Chrome DevTools — Application

---

## SC-023 — Verify Session Storage Progress Persistence and Reset

**Website:** https://jec.fish/demo/storage

**Objective:** Verify how the demo progress behaves during a browser tab session and after closing the tab.

**Preconditions:** The demo page is open with an initial progress of 0%.

**Steps:**
1. Open Chrome DevTools and select Application.
2. Inspect Local Storage and Session Storage.
3. Click the play button until progress reaches 80%.
4. Inspect the stored progress value.
5. Close the browser tab.
6. Reopen the demo website.

**Expected Result:**
Progress should be preserved within the same tab session and reset after the tab session ends, according to the demo's stated behavior.

**Actual Result:**
Progress increased from 0% to 40% and then to 80%. Session Storage contained `iec.demo.progress` with a value of `4` at 80%. After closing the tab and reopening the website, progress returned to 0%.

**Status:** Pass

**Evidence:** Chrome DevTools screenshots showing progress and Session Storage.

---

## SC-024 — Verify Login Session Persistence After Refresh

**Website:** https://the-internet.herokuapp.com/login

**Objective:** Verify that the user remains logged in after refreshing the secure area.

**Preconditions:** The login page is open.

**Steps:**
1. Log in using valid demo credentials.
2. Verify that the Secure Area page is displayed.
3. Inspect Cookies in Chrome DevTools.
4. Refresh the page.
5. Observe the displayed page.

**Expected Result:**
The user should remain logged in and the Secure Area page should remain accessible after refresh.

**Actual Result:**
The login succeeded and the Secure Area page was displayed. The `rack.session` cookie was present. After refreshing, the Secure Area page remained accessible.

**Status:** Pass

**Evidence:** Secure Area and Cookie screenshots.

---

## SC-025 — Verify Protected Page Access After Logout

**Website:** https://the-internet.herokuapp.com/login

**Objective:** Verify that a logged-out user cannot access the protected page.

**Preconditions:** The user is logged in.

**Steps:**
1. Click Logout.
2. Confirm that the login page is displayed.
3. Refresh the page.
4. Navigate directly to `https://the-internet.herokuapp.com/secure`.
5. Observe the displayed page and inspect the cookies.

**Expected Result:**
The user should not be able to access the Secure Area after logout.

**Actual Result:**
The login page was displayed after logout and remained visible after refresh. Direct navigation to `/secure` displayed the login form instead of the Secure Area. The `rack.session` cookie was still present.

**Status:** Pass

**Evidence:** Login page and Cookie screenshots.

---

## Test Summary

- Total Scenarios: 3
- Passed: 3
- Failed: 0
- Confirmed Bugs: 0

**Conclusion:**

The observed browser storage and authentication behaviors were consistent with the tested expectations. The presence of a session cookie after logout did not indicate continued access to the protected page.