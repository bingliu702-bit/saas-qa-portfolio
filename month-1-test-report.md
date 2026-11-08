# Month 1 Manual QA Test Report

## 1. Scope

This report summarizes the manual testing activities completed during the first month of QA training.

The test scope includes login testing, registration form testing, shopping cart functionality testing, and compatibility and usability checks across multiple practice websites.

## 2. Test Environment

- Operating System: Windows 11
- Browser: Google Chrome
- Testing Method: Manual Testing
- Responsive Testing Tool: Chrome DevTools
- Test Websites: Multiple practice websites, including Stan Store, AcademyBugs, and The Internet

Responsive checks were performed using simulated viewport sizes. Testing on physical mobile devices was not confirmed.

## 3. Test Approach

The main testing approaches included manual functional testing, exploratory testing, and responsive testing.

Some test scenarios were designed using equivalence partitioning and boundary value analysis.

Test results were documented using test scenarios, execution reports, screenshots, and bug reports where available.

## 4. Test Execution Summary

### Verified Records

| Source | Passed | Failed | Blocked |
|---|---:|---:|---:|
| Day 23 | 3 | 0 | 2 |
| Day 24 | TBD | TBD | TBD |
| Day 25 | 3 | 0 | 0 |

Day 23 recorded five test scenarios. Three were executed and passed, while two were blocked.

Day 25 included three manual functional checks, all of which passed. No actual software fix was verified.

The overall monthly execution totals remain unverified because not all historical execution records have been audited.

## 5. Defect Summary

Four bug reports are documented in the project:

- BR-001: Incorrect shopping cart grand total
- BR-002: Currency selection crash
- BR-003: Russian text displayed on an English login page
- BR-004: Shopping cart quantity resets after update

The current resolution status of these reported defects has not been reverified.

No new defects were confirmed during Day 23 testing.

## 6. Risks

- Some test scenarios could not be executed because a valid test account was unavailable.
- Simulated responsive testing may not reveal issues specific to physical devices.
- Incomplete execution records limit the accuracy of overall monthly statistics.
- Previously reported defects may require retesting to determine their current status.

## 7. Limitations

- Two Day 23 test scenarios were blocked because no valid test account was available.
- Day 24 execution counts require verification.
- Day 25 checks did not verify a confirmed developer fix.
- Backend systems and databases were not directly verified as part of the documented registration tests.
- A complete monthly pass rate cannot be calculated from the currently verified records.

## 8. Recommendations

- Retest blocked scenarios when the required test account becomes available.
- Review previously reported defects and verify their current status.
- Complete the audit of historical execution records before publishing final monthly totals.
- Continue documenting test evidence and clearly distinguish observed results from assumptions.

## 9. Conclusion

During the first month, manual QA activities covered several functional areas across multiple practice websites.

The available records demonstrate experience with test design, manual execution, defect reporting, exploratory testing, and responsive checks.

However, the available evidence does not support a claim that all tested functionality is defect-free or that all planned tests were completed.