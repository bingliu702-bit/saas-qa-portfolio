# SC-021 — Verify HTTP Requests During Successful Login

**Test Website:** https://the-internet.herokuapp.com/login

**Test Date:** 2026-10-12

**Test Type:** Functional Testing / Network Inspection

**Status:** Pass

### Objective

Verify that a user can log in with valid test credentials and that the browser completes the expected login and redirect flow.

### Preconditions

- Google Chrome is open.
- The login page is accessible.
- Valid test credentials are available.
- Chrome DevTools is open with the Network tab selected.
- Keep log is enabled.

### Test Steps

1. Open the login page.
2. Open Chrome DevTools and select the Network tab.
3. Enable Keep log.
4. Enter valid test credentials.
5. Click the Login button.
6. Locate the `authenticate` request in the Network panel.
7. Inspect the request method, status code, and Location response header.
8. Inspect the redirected `secure` page request.
9. Check the login result displayed on the page.

### Expected Result

1. The user should be able to log in with valid credentials.
2. The application should redirect the user to the secure page.
3. The secure page should load successfully.
4. A successful login message should be displayed.

### Actual Result

1. The browser submitted a POST request to `https://the-internet.herokuapp.com/authenticate`.
2. The server returned `303 See Other`.
3. The Location response header pointed to `https://the-internet.herokuapp.com/secure`.
4. The redirected `secure` page request returned `200 OK`.
5. The secure page displayed a successful login message.

### Test Result

**Pass**

The observed login behavior matched the expected functional outcome. No login-related defect was identified during this test.

### Evidence

- Network screenshot showing `authenticate` (303) and `secure` (200).
- Headers screenshot showing the POST method and 303 status.
- Response headers screenshot showing the Location value.
- Secure page screenshot showing the successful login message.

### Notes

- HTTP 303 is a redirect response and does not indicate a failure by itself.
- An HTTP 200 response does not guarantee that all application functions are defect-free.
- Test credentials, cookies, and session tokens must not be included in public evidence.

---

# SC-022 — Verify HTTP Requests During Logout

**Test Website:** https://the-internet.herokuapp.com/login

**Test Date:** 2026-10-12

**Test Type:** Functional Testing / Network Inspection

**Status:** Pass

### Objective

Verify that clicking the Logout button redirects the user from the secure page to the login page.

### Preconditions

- The user is logged in.
- The secure page is displayed.
- Chrome DevTools is open with the Network tab selected.
- Keep log is enabled.

### Test Steps

1. Open the secure page after a successful login.
2. Open Chrome DevTools and select the Network tab.
3. Enable Keep log.
4. Click the Logout button.
5. Locate the `logout` request in the Network panel.
6. Inspect the request status code.
7. Locate the redirected `login` page request.
8. Check the page displayed after logout.

### Expected Result

1. The user should be redirected to the login page after clicking Logout.
2. The login page should load successfully.
3. The user should no longer be viewing the secure page.

### Actual Result

1. After clicking Logout, the browser sent a request to `/logout`.
2. The `/logout` request returned HTTP 302.
3. The redirected `/login` request returned HTTP 200.
4. The login page was displayed after logout.

### Test Result

**Pass**

The observed logout and redirect behavior matched the expected page-navigation outcome.

### Evidence

- Network screenshot showing `logout` (302) and `login` (200).

### Notes

- HTTP 302 indicates a redirect, not necessarily an error.
- This test confirms the observed logout navigation flow. It does not verify whether the previous session was invalidated or whether the secure page can still be accessed without logging in again.