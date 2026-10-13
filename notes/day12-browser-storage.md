# Day 12 — Browser Storage, Cookies, and Sessions

## 1. Learning Objectives

- Understand the differences between Local Storage, Session Storage, and Cookies.
- Use Chrome DevTools to inspect browser storage.
- Observe how stored data changes during user interactions.
- Verify login persistence and logout behavior.
- Record actual observations without assuming that every unusual behavior is a bug.

## 2. Browser Storage Basics

### Local Storage

Local Storage stores data in the browser for a specific origin.

- Data normally remains after refreshing the page.
- Data normally remains after closing and reopening the browser.
- Data is not automatically sent with HTTP requests.
- Common uses include user preferences and interface settings.

### Session Storage

Session Storage stores data for a specific origin within a browser tab's page session.

- Data normally remains after refreshing the page.
- Data is normally removed when the tab's page session ends.
- Data is not automatically sent with HTTP requests.
- Common uses include temporary progress and page-specific state.

### Cookies

Cookies are small pieces of data associated with websites.

- Cookies may be temporary or persistent.
- Matching cookies are normally sent automatically with HTTP requests.
- Cookies can be used for session management and other purposes.
- A cookie's presence does not necessarily mean the user is authenticated.

## 3. Test Environment

- Operating System: Windows 11
- Browser: Google Chrome
- Tool: Chrome DevTools — Application
- Test Date: October 13, 2026

## 4. Practical Test A — Local Storage and Session Storage

**Website:** https://jec.fish/demo/storage

**Test Objective:**

Observe how the demo application stores progress in the browser.

**Test Steps:**

1. Open the demo website.
2. Open Chrome DevTools.
3. Select Application.
4. Inspect Local Storage and Session Storage.
5. Click the play button to increase progress.
6. Observe the progress value and storage entries.
7. Close the browser tab.
8. Reopen the demo website.

**Actual Observations:**

- The progress increased from 0% to 40% and then to 80%.
- The Local Storage table did not show a progress entry during the observations.
- Session Storage contained the key `iec.demo.progress` with the value `4` when the displayed progress was 80%.
- After closing the tab and reopening the website, the progress returned to 0%.

**Result:** Pass — the observed behavior was consistent with temporary session-based progress storage.

**Important Note:**

The displayed percentage and the stored numeric value were different representations of progress. The exact relationship should not be assumed without checking the application's implementation.

## 5. Practical Test B — Login Session and Cookies

**Website:** https://the-internet.herokuapp.com/login

**Test Objective:**

Observe the browser's session cookie and verify access to the secure area before and after logout.

**Test Steps:**

1. Open the login page.
2. Inspect the website's cookies in Chrome DevTools.
3. Log in with the valid demo credentials.
4. Observe the secure area and the `rack.session` cookie.
5. Refresh the secure area.
6. Click Logout.
7. Refresh the login page.
8. Navigate directly to `/secure`.

**Actual Observations:**

- The login succeeded and the Secure Area page was displayed.
- The secure area remained accessible after refreshing while logged in.
- A cookie named `rack.session` was observed after login.
- After logout, the login page was displayed.
- The `rack.session` cookie was still present after logout.
- Refreshing after logout did not restore the secure area.
- Attempting to access `/secure` after logout displayed the login page rather than the secure area.

**Result:** Pass — the logged-out user could not access the secure area in the observed test.

**Important Note:**

A session cookie may remain in the browser after logout. Its presence alone does not prove that the user is still authenticated. The server-side session handling was not directly inspected.

## 6. Key Learning Points

1. Local Storage, Session Storage, and Cookies have different lifetimes and behaviors.
2. Session Storage can preserve temporary progress during a tab's page session.
3. Cookies can support login sessions, but their presence does not guarantee authentication.
4. Refreshing a page and closing a tab are different test conditions.
5. QA testers should compare expected behavior with actual observations and collect evidence before reporting a defect.

## 7. Day 12 Conclusion

I used Chrome DevTools to inspect browser storage and cookies on two practice websites.

I observed temporary progress stored in Session Storage and verified that access to a protected page was not restored after logout.

No confirmed application defect was identified during these exercises.