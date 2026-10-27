# Day 20 - Week 3 QA Review

## 1. Learning Objectives

Practice test design techniques, execute test scenarios, analyze actual results, and document defects with evidence.

## 2. Test Design Techniques

During Week 3, I practiced five test design techniques:

1. Equivalence Partitioning
2. Boundary Value Analysis
3. Decision Table Testing
4. State Transition Testing
5. Exploratory Testing

## 3. Practical Testing

I practiced manual testing using The Internet and AcademyBugs.

I designed and executed test scenarios for login forms, input fields, dynamic controls, and shopping cart functionality.

I learned to distinguish test design from test execution.

I also practiced comparing expected results with actual results.

## 4. Key Finding

During Day 20, I found a shopping cart quantity update issue.

The product details page allowed a purchase quantity of up to 10.

However, when I changed the shopping cart quantity from 5 to 6 and clicked UPDATE, the quantity reset to 2.

I reproduced the behavior and documented it in BR-004.

## 5. Bug Reporting

I created BR-004 with:

- Steps to Reproduce
- Expected Result
- Actual Result
- Environment
- Severity and Priority (Provisional)
- Screenshot Evidence

The previously reported cart total issue was documented separately in BR-001.

## 6. Key Lessons

- Test cases should be based on documented business rules when available.
- Actual results must be based on observed behavior.
- A failed test does not automatically confirm a defect.
- Unexpected behavior should be investigated and reproduced.
- Screenshots and clear reproduction steps improve bug reports.
- Test coverage should be distinguished from untested areas.

## 7. Areas for Improvement

- Write shorter and clearer English test steps.
- Record test preconditions more consistently.
- Improve test evidence organization.
- Practice explaining defects in English.
- Continue improving test result analysis.

## 8. Week 3 Summary

During Week 3, I practiced test design, manual test execution, exploratory testing, and defect reporting.

I improved my ability to analyze unexpected behavior and document reproducible issues.

My next goal is to apply these skills consistently in future QA testing tasks.