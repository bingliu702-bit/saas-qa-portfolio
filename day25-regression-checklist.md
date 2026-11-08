# Day 25 - Regression Testing Checklist

## Project Information

- Project: Stan Store Registration Testing
- Test Type: Regression Testing Practice / Manual Functional Checks
- Change: Hypothetical password validation logic update
- Execution Status: 3/3 Checks Executed - Passed
- Test Environment: Windows 11, Google Chrome
- Test URL: https://admin.stan.store/register

## Regression Checklist

| ID | Check Item | Priority | Status |
|---|---|---|---|
| RC-01 | Verify whether the system displays an error message when an invalid password is entered. | High | Passed |
| RC-02 | Verify that the system accepts passwords that comply with the rules. | High | Passed |
| RC-03 | Verify that the Next button allows you to proceed to the next step when valid data is entered in all required fields. | High | Passed |

## Test Execution Summary

- Total Checks: 3
- Executed: 3
- Passed: 3
- Failed: 0
- Blocked: 0
- Not Run: 0

## RC-01 Execution Record

- Test Data: `abc`
- Expected Result: An invalid password should trigger an error message.
- Actual Result: After entering `abc` and moving focus away, the Password field displayed a red validation state and the message "Password must be at least 6 characters".
- Status: Passed
- Scope: Only the tested input `abc`.
- Evidence: Manual observation; no screenshot reference recorded.

## RC-02 Execution Record

- Test Data: `Test123456`
- Expected Result: The system should accept the password without displaying a validation error.
- Actual Result: No password validation error message was displayed after entering `Test123456`.
- Status: Passed
- Scope: Only the tested password `Test123456`; full password requirements have not been confirmed.
- Evidence: Manual observation; no screenshot reference recorded.

## RC-03 Execution Record

- Test Data: Valid input data entered in all required registration fields, as reported during manual testing.
- Expected Result: The Next button should allow the user to proceed to the next registration step when all required fields contain valid data.
- Actual Result: After clicking Next, the page navigated to "Connect your social accounts to your store".
- Status: Passed
- Scope: Navigation to the next registration step only. Complete account registration was not verified.
- Evidence: Manual observation; no screenshot reference recorded.

## Notes and Limitations

- This checklist was designed around a hypothetical password validation change.
- All three checks were executed as manual functional checks on the registration page.
- No actual developer fix or release version has been confirmed.
- Full password validation requirements have not been independently confirmed.
- The results apply only to the observed test inputs and actions.
- The results do not establish that an actual software fix has passed formal regression testing.
- No screenshot references were recorded for these three checks.

## Final Conclusion

All three planned manual checks were executed and recorded as Passed based on the observed results. No failures were observed in these specific checks. This exercise demonstrates regression checklist preparation and manual test execution, but does not constitute formal verification of a confirmed software fix.