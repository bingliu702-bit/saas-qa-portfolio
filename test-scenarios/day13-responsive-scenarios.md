# Day 13 - Responsive Layout Testing

## Test Environment
- Website: https://the-internet.herokuapp.com/login
- Browser: Google Chrome
- Device emulation: Chrome DevTools (Responsive)
- Viewports: 375 x 667, 768 x 1024, 1366 x 768

## SC-023: Verify Login Page Layout at Different Viewport Sizes

**Objective:** Verify that the login page remains readable and usable at different viewport sizes.

**Preconditions:** The login page is open in Chrome DevTools responsive mode.

**Steps:**
1. Set the viewport to 375 x 667.
2. Observe the heading, instructions, input fields, and Login button.
3. Repeat at 768 x 1024.
4. Repeat at 1366 x 768.

**Expected Result:**
The login form should remain visible, readable, and usable without overlapping or clipped essential controls.

**Actual Result:**
At all three tested viewport sizes, the login heading, instructions, username field, password field, and Login button were visible. No overlapping or clipped essential controls were observed in the captured views.

**Status:** Pass (for the observed layout checks)

**Evidence:**
- ../evidence/day13-responsive/375-login.png
- ../evidence/day13-responsive/768-login.png
- ../evidence/day13-responsive/1366-login.png

## SC-024: Verify Secure Area Layout After Login

**Objective:** Verify that the secure area remains readable and usable after a successful login at different viewport sizes.

**Preconditions:** The login page is open and valid demo credentials are available.

**Steps:**
1. Set the viewport to 375 x 667.
2. Log in using valid demo credentials.
3. Observe the success message, Secure Area heading, and Logout button.
4. Repeat at 768 x 1024 and 1366 x 768.

**Expected Result:**
The secure area content and Logout button should remain visible and usable without overlapping or clipped essential controls.

**Actual Result:**
At all three tested viewport sizes, the secure area, login success message, and Logout button were visible. No overlapping or clipped essential controls were observed in the captured views.

**Status:** Pass (for the observed layout checks)

**Evidence:**
- ../evidence/day13-responsive/375-secure-area.png
- ../evidence/day13-responsive/768-secure-area.png
- ../evidence/day13-responsive/1366-secure-area.png

## Test Summary
- Viewport sizes tested: 3
- Test scenarios: 2
- Observed result: No visible layout issues in the captured login and secure area views.
- Limitation: These checks do not establish behavior on physical devices or across other browsers.
