# Day 02 — Equivalence Partitioning and Boundary Value Analysis

## 1. What Is Equivalence Partitioning?

Equivalence Partitioning (EP) is a test design technique that divides a large set of possible input data into several groups, or partitions.

We assume that data within the same partition will be processed by the system in a similar way. Therefore, it is usually unnecessary to test every possible value in a partition. Instead, representative values can be selected to improve testing efficiency.

### Valid Partition

A valid partition contains data that meets the defined system rules and should theoretically be accepted by the system.

For example, assume that a password must:

- Be 8–20 characters long
- Allow letters, numbers, and special characters

Examples of valid inputs:

- `Test1234`
- `Password@123`
- An 8-character password
- A 20-character password

### Invalid Partition

An invalid partition contains data that does not meet the defined system rules and should theoretically be rejected by the system.

Examples:

- An empty password
- A password with only 7 characters
- A password longer than 20 characters
- Characters that are not allowed by the system
- A password containing only spaces
- An incorrect password

---

## 2. What Are Boundary Values?

Boundary Value Analysis (BVA) focuses on values at or near the boundaries of a rule because defects frequently occur around minimum and maximum limits.

Assume that the password length must be between 8 and 20 characters.

The following values should be tested:

| Test Position | Password Length | Expected Result |
|---|---:|---|
| Below minimum | 7 | Rejected |
| Minimum | 8 | Accepted |
| Just above minimum | 9 | Accepted |
| Just below maximum | 19 | Accepted |
| Maximum | 20 | Accepted |
| Above maximum | 21 | Rejected |

These six positions can be remembered as:

- Minimum − 1
- Minimum
- Minimum + 1
- Maximum − 1
- Maximum
- Maximum + 1

---

## 3. Login Page Testing Examples

| # | Input Condition | Classification | Expected Result |
|---:|---|---|---|
| 1 | Correct username and correct password | Valid partition | Login succeeds |
| 2 | Correct username and incorrect password | Invalid partition | Login fails and an appropriate message is displayed |
| 3 | Username is empty | Invalid partition | Login is prevented and a required-field message is displayed |
| 4 | Password is empty | Invalid partition | Login is prevented and a required-field message is displayed |
| 5 | Both username and password are empty | Invalid partition | Login is prevented and an appropriate required-field message is displayed |
| 6 | Password contains leading and trailing spaces | Product rule requires confirmation | The system should handle spaces according to the defined requirements |
| 7 | Password exceeds the maximum allowed length | Invalid partition or out-of-boundary input | The system should handle the input safely and should not crash |
| 8 | Password contains special characters | Depends on the password rules | The system should accept or reject the input according to the defined rules |
| 9 | Password length equals the minimum allowed length | Minimum boundary | The system should handle the input according to the defined rules |
| 10 | Password length is one character below the minimum | Below minimum boundary | The input should be rejected and an appropriate message should be displayed |

---

## 4. Important Considerations During Testing

If the product requirements do not clearly specify the minimum password length, maximum password length, or allowed characters, testers should not invent rules and immediately classify unexpected behavior as a bug.

The correct approach is to:

1. Record the input data.
2. Record the actions performed.
3. Record the actual result.
4. Mark the case as **"Product rule requires confirmation."**
5. Obtain clarification of the requirements before determining whether the result should be considered Pass or Fail.

---

## 5. What I Need to Know

### Must Remember

- **Valid partition:** A group of valid input data that meets the defined rules.
- **Invalid partition:** A group of invalid input data that does not meet the defined rules.
- **Boundary:** The edge of a defined rule or input range.
- **Boundary values:** Commonly include the values just below, at, and just above the minimum and maximum limits.

### Only Need to Understand

The purpose of Equivalence Partitioning is not to reduce testing quality. It is to improve testing efficiency by using representative values instead of testing every possible value.

### Practical Applications

Use Equivalence Partitioning and Boundary Value Analysis when designing test scenarios for:

- Login
- Registration
- Search
- Quantity
- Amount
- Date
- Form inputs
