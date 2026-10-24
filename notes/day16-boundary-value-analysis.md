# Day 16 — Boundary Value Analysis (BVA)

## 1. Learning Objective

Practice Boundary Value Analysis (BVA) by identifying values at and around minimum and maximum limits.

For an inclusive integer range, the six commonly selected boundary values are:

- min - 1
- min
- min + 1
- max - 1
- max
- max + 1

Boundary values help identify defects related to incorrect minimum and maximum limit checks.

## 2. Boundary Value Test Design

**Requirement Status: Assumed Requirements**

The following rules are hypothetical and have not been verified against a real application's requirements.

### 2.1 Username Length

**Assumed Rule:** A username must contain 6 to 12 characters, inclusive.

| Test ID | Boundary | Test Data | Expected Result | Actual Result |
|---|---|---|---|---|
| BV-001 | min - 1 | abcde | Invalid | Not Tested |
| BV-002 | min | abcdef | Valid | Not Tested |
| BV-003 | min + 1 | abcdefg | Valid | Not Tested |
| BV-004 | max - 1 | abcdefghijk | Valid | Not Tested |
| BV-005 | max | abcdefghijkl | Valid | Not Tested |
| BV-006 | max + 1 | abcdefghijklm | Invalid | Not Tested |

### 2.2 Product Quantity

**Assumed Rule:** An order must contain 2 to 8 items, inclusive. Only integers are allowed.

| Boundary | Test Data | Expected Result |
|---|---|---|
| min - 1 | 1 | Invalid |
| min | 2 | Valid |
| min + 1 | 3 | Valid |
| max - 1 | 7 | Valid |
| max | 8 | Valid |
| max + 1 | 9 | Invalid |

### 2.3 Booking Date

**Assumed Rule:** The booking date must be between November 1 and November 30, 2026, inclusive.

| Boundary | Test Data | Expected Result |
|---|---|---|
| min - 1 | 2026-10-31 | Invalid |
| min | 2026-11-01 | Valid |
| min + 1 | 2026-11-02 | Valid |
| max - 1 | 2026-11-29 | Valid |
| max | 2026-11-30 | Valid |
| max + 1 | 2026-12-01 | Invalid |

### 2.4 File Size

**Assumed Rule:** The maximum file size is 5 MiB (5,242,880 bytes), inclusive.

| Boundary | Test Data | Expected Result |
|---|---|---|
| max - 1 | 5,242,879 bytes | Valid |
| max | 5,242,880 bytes | Valid |
| max + 1 | 5,242,881 bytes | Invalid |

The minimum allowed file size is not specified.

## 3. Executed Test Scenarios

**Test Website:** The Internet — Inputs  
**Test Environment:** Windows 11, Google Chrome  
**Test Date:** October 24, 2026

The page provides a number input field, but no confirmed minimum or maximum value requirement was available during testing.

### SC-026 — Zero Input

**Scenario:** Verify the behavior of the number input field when entering 0.

**Test Data:** `0`

**Steps:**
1. Open the Inputs page.
2. Enter 0 in the number field.
3. Press Tab.

**Expected Result:** Not specified — the minimum allowed value is unknown.

**Actual Result:** The number 0 was displayed in the input field.

**Status:** Not Determined

### SC-027 — Negative Number Input

**Scenario:** Verify the behavior of the number input field when entering -1.

**Test Data:** `-1`

**Steps:**
1. Open the Inputs page.
2. Enter -1 in the number field.
3. Press Tab.

**Expected Result:** Not specified — the minimum allowed value is unknown.

**Actual Result:** The number -1 was displayed in the input field.

**Status:** Not Determined

### SC-028 — Positive Number Input

**Scenario:** Verify the behavior of the number input field when entering 1.

**Test Data:** `1`

**Steps:**
1. Open the Inputs page.
2. Enter 1 in the number field.
3. Press Tab.

**Expected Result:** Not specified — the minimum allowed value is unknown.

**Actual Result:** The number 1 was displayed in the input field.

**Status:** Not Determined

## 4. Test Summary

- Practiced boundary value selection for username length, product quantity, booking dates, and file size.
- Designed test data based on clearly labeled assumed requirements.
- Observed the number input field with three values: 0, -1, and 1.
- Created three test scenarios: SC-026, SC-027, and SC-028.
- No confirmed boundary validation defect was identified.
- BR-009 was not created because there was insufficient evidence of a defect.

**Key Learning:** Test expectations must be based on documented or confirmed requirements. Actual results must be recorded from observed application behavior. A displayed input value does not, by itself, prove that the value satisfies a business rule.