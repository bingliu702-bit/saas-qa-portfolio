# Day 15 - Equivalence Partitioning

## 1. Test Objective

Practice equivalence partitioning by testing valid and invalid input data on two features of The Internet test website.

The selected features are:
- Form Authentication
- Number Input

## 2. Test Environment

- Website: https://the-internet.herokuapp.com/
- Operating System: Windows 11
- Browser: Google Chrome
- Testing Method: Manual Testing
- Test Design Technique: Equivalence Partitioning

## 3. Login Equivalence Partitions

Test Page: https://the-internet.herokuapp.com/login

| Partition ID | Description | Test Data | Expected Result | Actual Result | Status |
|---|---|---|---|---|---|
| V1 | Valid credentials | Valid username and password | Login succeeds | Secure Area displayed with a success message | PASS |
| I1 | Invalid username | Invalid username and valid password | Login is rejected | Username error message displayed | PASS |
| I2 | Invalid password | Valid username and invalid password | Login is rejected | Password error message displayed on retest | PASS (Retest) |

### Login Test Observations

- SC-022: Valid credentials allowed access to the Secure Area.
- SC-023: Invalid username was rejected with the message "Your username is invalid!".
- SC-024: Invalid password was rejected with the message "Your password is invalid!" on retest.
- During the initial SC-024 test, a username error message was observed. The cause was not confirmed, and the issue was not reproduced during retesting.

## 4. Number Input Equivalence Partitions

Test Page: https://the-internet.herokuapp.com/inputs

The page does not specify a required numeric range or whether the field is mandatory. The following partitions are based on observed input behavior.

| Candidate Partition | Test Data | Actual Observation | Assessment |
|---|---|---|---|
| Positive integer | 25 | Value was accepted and retained | Accepted |
| Negative integer | -5 | Value was accepted and retained | Accepted |
| Decimal number | 3.5 | Value was accepted and retained | Accepted |
| Alphabetic characters | abc | Characters were not displayed | Rejected |
| Empty input | Empty | Field remained empty | Requirement unknown |

### Number Input Test Observation

SC-025: Verify Alphabetic Input Handling

**Test Purpose:** Verify that the number input field does not accept alphabetic characters.

**Steps to Reproduce:**
1. Open https://the-internet.herokuapp.com/inputs.
2. Click the Number input field.
3. Type `abc`.

**Expected Result:** The number input field should reject alphabetic characters.

**Actual Result:** The characters `abc` were not displayed in the input field. The field remained empty.

**Status:** PASS

## 5. Test Summary

- Two website features were tested: Form Authentication and Number Input.
- Valid and invalid login credentials were tested.
- Numeric, alphabetic, and empty input behaviors were observed.
- No new defects were confirmed during Day 15 testing.
- One inconsistent login error message was observed during the initial test, but the issue was not reproduced during the retest.

## 6. Key Learning

Equivalence partitioning helps select representative test data and reduce unnecessary duplicate test cases.

Test results should be based on observed behavior and documented requirements. Unknown business rules should not be treated as confirmed facts.