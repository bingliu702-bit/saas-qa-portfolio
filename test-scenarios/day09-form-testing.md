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
  
---

## SC-017: Verify Checkbox Selection and Deselection

### Test Objective
Verify that checkboxes can be selected and deselected correctly and that each checkbox can be selected independently.

### Preconditions
- The Checkbox test page is accessible.
- `checkbox 1` and `checkbox 2` are displayed.

### Test Data
- `checkbox 1`
- `checkbox 2`

### Test Steps
1. Open the Checkbox test page.
2. Observe the current state of `checkbox 1` and `checkbox 2`.
3. Click an unchecked checkbox.
4. Observe its state.
5. Click the other checkbox and observe whether both checkboxes can be selected at the same time.
6. Click a selected checkbox again.
7. Observe whether it returns to the unchecked state.

### Expected Result
- Clicking an unchecked checkbox should change it to the selected state.
- `checkbox 1` and `checkbox 2` should be independently selectable.
- Clicking a selected checkbox again should return it to the unchecked state.

### Actual Result
- Clicking an unchecked checkbox changed it to a selected state with a visible check mark.
- `checkbox 1` and `checkbox 2` could be selected at the same time.
- Clicking a selected checkbox again removed the check mark and returned it to the unchecked state.

### Status
**Pass**

---

## SC-018: Verify Country/Region Code Dropdown Selection

### Test Objective
Verify that the country/region code dropdown can be opened, an option can be selected, and the current selection can be changed to another option.

### Preconditions
- The Stan registration page is accessible.
- The phone number field and country/region code dropdown are displayed.

### Test Data
- `Afghanistan +93`
- `Albania +355`

### Test Steps
1. Open the Stan registration page.
2. Click the country/region code dropdown next to the phone number field.
3. Observe the dropdown list.
4. Select `Afghanistan +93`.
5. Observe the selected country/region and calling code.
6. Open the dropdown again.
7. Select `Albania +355`.
8. Observe the selected country/region and calling code.

### Expected Result
- The dropdown should open and display available countries/regions with their calling codes.
- After selecting `Afghanistan +93`, the current selection should update to Afghanistan with calling code `+93`.
- After selecting `Albania +355`, the current selection should update to Albania with calling code `+355`, replacing the previous selection.

### Actual Result
- The dropdown opened successfully and displayed countries/regions with their calling codes.
- After selecting `Afghanistan +93`, the displayed calling code changed to `+93`.
- After selecting `Albania +355`, the displayed calling code changed to `+355`, replacing the previous selection.

### Status
**Pass**

### Evidence
- Screenshot: Country/region code dropdown expanded.
- Screenshot: `Afghanistan +93` selected.
- Screenshot: `Albania +355` selected after changing the selection.

### Evidence
- Screenshot: `checkbox 1` selected and `checkbox 2` deselected.
- Screenshot: Both checkboxes selected.
- Screenshot: Both checkboxes deselected.
