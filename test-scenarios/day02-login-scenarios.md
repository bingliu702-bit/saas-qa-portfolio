
# Day 02 — Login Test Scenarios

## Test Information

- Test target: P4 login page
- Test date:
- Browser:
- Operating system: Windows
- Tester: bingliu702-bit
- Status options: Not Run / Pass / Fail / Blocked

> Expected results must be checked against the actual product requirements. If a password rule is not documented, record “Requirement needs confirmation” instead of immediately reporting a bug.

---

## SC-006: Log in with valid credentials

- **Objective:** Verify that a registered user can log in successfully.
- **Test type:** Valid partition
- **Preconditions:**
  - The login page is available.
  - A valid test account has been prepared.
- **Test data:**
  - Username: `[Valid test username]`
  - Password: `[Valid test password — do not publish the real password]`
- **Steps:**
  1. Open the login page.
  2. Enter a valid username.
  3. Enter the correct password.
  4. Click the **Login** button.
- **Expected result:**
  - Login succeeds.
  - The user is redirected to the correct page.
  - No error message is displayed.
- **Actual result:** To be completed after execution.
- **Status:** Not Run
- **Evidence:** To be added.

---

## SC-007: Log in with an incorrect password

- **Objective:** Verify that the system rejects an incorrect password.
- **Test type:** Invalid partition
- **Preconditions:**
  - The login page is available.
  - A valid test username has been prepared.
- **Test data:**
  - Username: `[Valid test username]`
  - Password: `WrongPassword123!`
- **Steps:**
  1. Open the login page.
  2. Enter a valid username.
  3. Enter an incorrect password.
  4. Click the **Login** button.
- **Expected result:**
  - Login is rejected.
  - The user remains on the login page.
  - A clear and appropriate error message is displayed.
  - The message does not reveal sensitive account information.
- **Actual result:** To be completed after execution.
- **Status:** Not Run
- **Evidence:** To be added.

---

## SC-008: Submit empty username and password fields

- **Objective:** Verify the validation of required login fields.
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
  - Login does not succeed.
  - Required-field validation is displayed or submission is prevented.
  - The page does not crash.
- **Actual result:** To be completed after execution.
- **Status:** Not Run
- **Evidence:** To be added.

---

## SC-009: Enter a password with leading and trailing spaces

- **Objective:** Observe how the system handles spaces before and after a password.
- **Test type:** Partition requiring product-rule confirmation
- **Preconditions:**
  - The login page is available.
  - A valid test account has been prepared.
- **Test data:**
  - Username: `[Valid test username]`
  - Password: `[Valid password with one leading and one trailing space]`
- **Steps:**
  1. Open the login page.
  2. Enter a valid username.
  3. Enter the valid password with a space before and after it.
  4. Click the **Login** button.
- **Expected result:**
  - The system handles spaces according to the documented requirement.
  - The page does not crash or display a broken layout.
  - If no requirement is available, mark the behavior as **Requirement needs confirmation**.
- **Actual result:** To be completed after execution.
- **Status:** Not Run
- **Evidence:** To be added.

---

## SC-010: Enter an excessively long password

- **Objective:** Verify that the password field safely handles an excessively long value.
- **Test type:** Boundary / Invalid partition
- **Precondition:** The login page is available.
- **Test data:**
  - Username: `[Valid test username]`
  - Password: `[100-character value]`
- **Steps:**
  1. Open the login page.
  2. Enter a valid username.
  3. Enter a 100-character value in the password field.
  4. Click the **Login** button.
- **Expected result:**
  - The page does not crash, freeze, or display a broken layout.
  - The system limits the input or safely rejects the login attempt according to its password rules.
  - If the maximum length is undocumented, record the observed behavior and mark the rule for confirmation.
- **Actual result:** To be completed after execution.
- **Status:** Not Run
- **Evidence:** To be added.

---

## SC-011: Enter special characters in the password field

- **Objective:** Verify that the password field safely handles special characters.
- **Test type:** Valid or invalid partition depending on product rules
- **Precondition:** The login page is available.
- **Test data:**
  - Username: `[Valid test username]`
  - Password: `!@#$%^&*()_+-=[]{}`
- **Steps:**
  1. Open the login page.
  2. Enter a valid username.
  3. Enter special characters in the password field.
  4. Click the **Login** button.
- **Expected result:**
  - The page does not crash or display a system error.
  - The input is accepted or rejected according to the documented password rules.
  - The password is not displayed as plain text by default.
- **Actual result:** To be completed after execution.
- **Status:** Not Run
- **Evidence:** To be added.

---

## SC-012: Verify password masking

- **Objective:** Verify that the password is protected from casual visual exposure.
- **Test type:** Security and usability check
- **Precondition:** The login page is available.
- **Test data:**
  - Password: `TestPassword123!`
- **Steps:**
  1. Open the login page.
  2. Enter the test password.
  3. Observe how the password is displayed.
  4. If a show/hide password control is available, click it and observe the result.
- **Expected result:**
  - The password is masked by default.
  - A show/hide control, if provided, changes the visibility correctly.
  - The password is not exposed unexpectedly.
- **Actual result:** To be completed after execution.
- **Status:** Not Run
- **Evidence:** To be added.

---

## Execution Summary

| Scenario | Status | Notes |
|---|---|---|
| SC-006 | Not Run | |
| SC-007 | Not Run | |
| SC-008 | Not Run | |
| SC-009 | Not Run | |
| SC-010 | Not Run | |
| SC-011 | Not Run | |
| SC-012 | Not Run | |
