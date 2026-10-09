## SC-015: Verify Email Field Validation

### Test Objective
Verify that the email field correctly validates valid and invalid email formats.

### Preconditions
- The Stan registration page is accessible.
- The email field is displayed and available for input.

### Test Data

| Type | Test Data |
|---|---|
| Invalid | `abc` |
| Invalid | `415335@gmail` |
| Invalid | `test@` |
| Valid format | `yuyu@gmail.com` |

### Test Steps
1. Open the Stan registration page.
2. Enter `abc` in the email field.
3. Observe the email field and validation message.
4. Clear the email field.
5. Repeat the test with `415335@gmail` and `test@`.
6. Enter `yuyu@gmail.com` as a valid-format email address.
7. Observe the email field and validation behavior.

### Expected Result
- Invalid email formats should be rejected with an appropriate validation message.
- A valid email format should not trigger the invalid-email-format validation message.

### Actual Result
- `abc`, `415335@gmail`, and `test@` triggered the validation message:
  **"Please enter a valid email address"**
- The email field was highlighted in red for all three invalid inputs.
- `yuyu@gmail.com` did not trigger the invalid-email-format validation message.

### Status
**Pass**

### Evidence
- Screenshot: Invalid email format `abc`
- Screenshot: Invalid email format `415335@gmail`
- Screenshot: Invalid email format `test@`
- Screenshot: Valid email format `yuyu@gmail.com`

---

## SC-016: Verify Password Visibility Toggle

### Test Objective
Verify that the password field masks the password by default and that the visibility toggle correctly shows and hides the password.

### Preconditions
- The Stan registration page is accessible.
- The password field and visibility toggle are displayed and available.

### Test Data
`TestPassword123!`

### Test Steps
1. Open the Stan registration page.
2. Enter `TestPassword123!` in the password field.
3. Observe how the password is displayed by default.
4. Click the visibility icon on the right side of the password field.
5. Observe the password display.
6. Click the visibility icon again.
7. Observe the password display again.

### Expected Result
- The password should be masked by default.
- After clicking the visibility icon once, the password should be displayed in plain text.
- After clicking the visibility icon again, the password should be masked again.

### Actual Result
- The password was masked with dots by default.
- After clicking the visibility icon once, `TestPassword123!` was displayed in plain text.
- After clicking the visibility icon again, the password was masked with dots again.

### Status
**Pass**

### Evidence
- Screenshot: Password masked by default.
- Screenshot: Password displayed in plain text after clicking the visibility icon.
- Screenshot: Password masked again after clicking the visibility icon a second time.
