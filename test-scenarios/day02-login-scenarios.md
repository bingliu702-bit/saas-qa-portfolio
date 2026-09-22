# Day 02 — Login Test Scenarios
## Test Information

- Test target: The Internet — Form Authentication
- Test URL: https://the-internet.herokuapp.com/login
- Test date: 2026-09-22
- Browser: Google Chrome 153.0.8010.53
- Operating system: Windows 11
- Tester: bingliu702-bit
- Status options: Not Run / Pass / Fail / Blocked
---

## SC-006: Log in with valid credentials
- **Objective:** Verify that a registered user can log in successfully.
- **Test type:** Valid partition
- **Preconditions:**
  - The login page is available.
  - A valid test account has been prepared.
  - The network connection is available.
- **Test data:**
  - Username: `tomsmith`
  - Password: `[Valid test password]`
- **Steps:**
  1. Open the login page.
  2. Enter `tomsmith` in the username field.
  3. Enter the valid password in the password field.
  4. Click the **Login** button.
- **Expected result:**
  - Login succeeds.
  - The user is redirected to the secure area.
  - A successful login message is displayed.
  - No error message is displayed.
- **Actual result:**
  - Login succeeded.
  - The user was redirected to the secure area.
  - A green success message stating that the user had logged into the secure area was displayed.
  - No error message was displayed.
- **Status:** Pass
- **Evidence:** Screenshot showing the secure area and the successful login message.

<img width="1122" height="490" alt="image" src="https://github.com/user-attachments/assets/2b5480cb-0a6d-46e5-9b75-11c06a99ae45" />
---

## SC-007: Log in with an incorrect password
- **Objective:** Verify that the system rejects an incorrect password.
- **Test type:** Invalid partition
- **Preconditions:**
  - The login page is available.
  - A valid test username has been prepared.
- **Test data:**
  - Username: `tomsmith`
  - Password: `WrongPassword123!`
- **Steps:**
  1. Open the login page.
  2. Enter `tomsmith` in the username field.
  3. Enter `WrongPassword123!` in the password field.
  4. Click the **Login** button.
- **Expected result:**
  - Login is rejected.
  - The user remains on the login page.
  - A clear and appropriate error message is displayed.
  - No sensitive account information is exposed.
- **Actual result:**
  - Login was rejected.
  - The user remained on the login page.
  - A red error message stating `Your password is invalid!` was displayed.
  - No password or other sensitive account information was displayed.
- **Status:** Pass
- **Evidence:** Screenshot showing the login page and the red `Your password is invalid!` message.

  <img width="1122" height="564" alt="image" src="https://github.com/user-attachments/assets/fc083554-6b33-4800-ba1d-2d198df6cc65" />

---

## SC-008: Submit empty username and password fields
- **Objective:** Verify how the login form handles empty required fields.
- **Test type:** Invalid partition
- **Precondition:** The login page is available.
- **Test data:**
  - Username: Empty
  - Password: Empty
- **Steps:**
  1. Open the login page.
  2. Leave the username and password fields empty.
  3. Click the **Login** button.
- **Expected result:**
  - Login is rejected.
  - Submission is prevented or a required-field validation message is displayed.
  - The page does not crash.
- **Actual result:**
  - Login was rejected.
  - The form submission was not prevented.
  - A red error message stating `Your username is invalid!` was displayed.
  - No specific required-field validation message was displayed.
  - The page did not crash.
- **Status:** Fail — Requirement needs confirmation
- **Evidence:** Screenshot showing the empty fields and the `Your username is invalid!` message.
<img width="1122" height="562" alt="image" src="https://github.com/user-attachments/assets/7a2c9499-8d42-459e-a617-fb5ccdd9d1a2" />
---

## SC-009: Enter a valid password with a trailing space
- **Objective:** Observe how the system handles a trailing space after a valid password.
- **Test type:** Input-handling test
- **Preconditions:**
  - The login page is available.
  - A valid test account has been prepared.
- **Test data:**
  - Username: `tomsmith`
  - Password: `SuperSecretPassword![One trailing space]`
- **Steps:**
  1. Open the login page.
  2. Enter `tomsmith` in the username field.
  3. Enter the valid password followed by one trailing space.
  4. Click the **Login** button.
- **Expected result:**
  - The system handles the trailing space consistently.
  - The page does not crash or display a broken layout.
  - If whitespace-handling requirements are unavailable, the observed behavior is documented for confirmation.
- **Actual result:**
  - Login was rejected.
  - The user remained on the login page.
  - A red error message stating `Your password is invalid!` was displayed.
  - The page did not crash or display a broken layout.
  - The system appeared to treat the trailing space as part of the password.
- **Status:** Pass
- **Evidence:** Screenshot showing the `Your password is invalid!` message after submitting the valid password with one trailing space.
<img width="1122" height="566" alt="image" src="https://github.com/user-attachments/assets/fa8bbf83-79cd-4525-ac8d-0b049f95df26" />
---

## SC-010: Enter an excessively long password

- **Objective:** Verify that the password field safely handles an excessively long value.
- **Test type:** Negative test / Invalid partition / Robustness test
- **Precondition:** The login page is available.
- **Test data:**
  - Username: `tomsmith`
  - Password: 100 uppercase `A` characters
- **Steps:**
  1. Open the login page.
  2. Enter `tomsmith` in the username field.
  3. Enter 100 uppercase `A` characters in the password field.
  4. Click the **Login** button.
- **Expected result:**
  - The page does not crash, freeze, or display a broken layout.
  - The system limits the input or safely rejects the login attempt.
  - If the maximum password length is undocumented, the observed behavior is recorded for confirmation.
- **Actual result:**
  - The form accepted the 100-character password input.
  - Login was rejected.
  - The user remained on the login page.
  - A red error message stating `Your password is invalid!` was displayed.
  - The page did not crash, freeze, or display a broken layout.
  - The maximum supported password length could not be confirmed from the available requirements.
- **Status:** Pass
- **Evidence:** Screenshot showing the login page and the `Your password is invalid!` message after submitting a 100-character password.
<img width="1122" height="623" alt="image" src="https://github.com/user-attachments/assets/065014e8-5961-4683-9857-c674fa08b6bc" />
---

## SC-011: Enter only special characters as the password
- **Objective:** Verify that the login form safely handles an incorrect password containing only special characters.
- **Test type:** Negative test / Invalid partition
- **Precondition:** The login page is available.
- **Test data:**
  - Username: `tomsmith`
  - Password: `!@#$%^&*()_+-=[]{}`
- **Steps:**
  1. Open the login page.
  2. Enter `tomsmith` in the username field.
  3. Enter `!@#$%^&*()_+-=[]{}` in the password field.
  4. Click the **Login** button.
- **Expected result:**
  - Login is rejected because the entered password does not match the valid password.
  - A clear error message is displayed.
  - The page does not crash, freeze, or display a system error.
- **Actual result:**
  - Login was rejected.
  - The user remained on the login page.
  - A red error message stating `Your password is invalid!` was displayed.
  - The page did not crash, freeze, or display a broken layout.
- **Status:** Pass
- **Evidence:** Screenshot showing the login page and the `Your password is invalid!` message after submitting a password containing only special characters.
<img width="1122" height="635" alt="image" src="https://github.com/user-attachments/assets/1af16cd3-4d6a-4674-8d04-f0bfc3de6f09" />
---

## SC-012: Verify password masking
- **Objective:** Verify that the password is protected from casual visual exposure.
- **Test type:** Security and usability check
- **Precondition:** The login page is available.
- **Test data:**
  - Username: `tomsmith`
  - Password: `TestPassword123!`
- **Steps:**
  1. Open the login page.
  2. Enter `tomsmith` in the username field.
  3. Enter `TestPassword123!` in the password field.
  4. Observe how the password is displayed.
  5. Check whether a show/hide password control is available.
- **Expected result:**
  - The password is masked by default.
  - The password is not unexpectedly displayed as plain text.
  - If a show/hide control is provided, it changes the password visibility correctly.
- **Actual result:**
  - The entered password was displayed as masked dots.
  - The password was not displayed as plain text.
  - No show/hide password control was available on the page.
- **Status:** Pass
- **Evidence:** Screenshot showing the username field and the password displayed as masked dots.
<img width="1122" height="498" alt="image" src="https://github.com/user-attachments/assets/cd21a53b-04f7-4819-80d9-7886d88962eb" />

---
| Scenario | Status | Notes |
|---|---|---|
| SC-006 | Pass | Login succeeded and the secure area was displayed. |
| SC-007 | Pass | Login was rejected and an invalid-password message was displayed. |
| SC-008 | Fail | Empty fields were submitted and a generic invalid-username message was displayed instead of required-field validation. Requirement needs confirmation. |
| SC-009 | Pass | Login was rejected when one trailing space was added to the valid password. |
| SC-010 | Pass | A 100-character password was handled safely and rejected without a crash or layout issue. |
| SC-011 | Pass | A password containing only special characters was handled safely and rejected with an appropriate error message. |
| SC-012 | Pass | The password was masked by default. No show/hide password control was available. |
