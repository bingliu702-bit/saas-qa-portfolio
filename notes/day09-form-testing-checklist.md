# Day 09 — Form Testing Checklist

This checklist is used as a reusable reference when testing common web forms such as registration, login, profile, and checkout forms.

> Note: Expected behavior should be based on product requirements. Do not assume validation rules that are not specified.

## 1. Text Input

- [ ] Verify that valid text can be entered and displayed correctly.
- [ ] If the field is required, verify the behavior when the field is left empty.
- [ ] Test reasonable special input, such as spaces, hyphens, or apostrophes where applicable.
- [ ] Test boundary values, such as very long input, when length requirements are known.

## 2. Password

- [ ] Verify that the password field accepts input.
- [ ] Verify that the password is masked by default.
- [ ] If the password is required, verify validation when it is left empty.
- [ ] If a visibility toggle is available, verify that the password can be shown and hidden correctly.
- [ ] If password rules are specified, test the defined length and format boundaries.

## 3. Checkbox

- [ ] Verify the initial checkbox state.
- [ ] Verify that an unchecked checkbox can be selected.
- [ ] If multiple selections are allowed, verify that multiple checkboxes can be selected independently.
- [ ] Verify that a selected checkbox can be deselected without unexpectedly affecting other checkboxes.

## 4. Dropdown

- [ ] Verify the default value or initial state.
- [ ] Verify that the dropdown opens and displays available options.
- [ ] Verify that an option can be selected.
- [ ] Verify that the selected option is displayed correctly after the dropdown closes.
- [ ] Verify that selecting another option correctly replaces the previous selection.

## 5. File Upload

- [ ] Submit without selecting a file and observe the validation behavior.
- [ ] Select a valid file and verify that the selected filename is displayed correctly.
- [ ] Upload a valid file and verify the upload result and system feedback.
- [ ] If file-type restrictions are specified, verify how unsupported file types are handled.

## 6. Form Submission

- [ ] Submit the form with all required fields containing valid data.
- [ ] Submit the form with a required field left empty.
- [ ] Submit the form with data that violates a specified format rule.
- [ ] Verify how the system handles repeated submission when applicable.

## Testing Principle

Test what is actually specified and observed.

If a product requirement is unclear, record the observed behavior and mark the requirement for confirmation instead of assuming that the behavior is a defect.
