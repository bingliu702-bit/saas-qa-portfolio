# Day 03 — Defect Severity and Priority


### Priority

Priority describes how urgently a defect should be fixed.

Priority may be influenced by business deadlines, release plans, customer commitments, affected users, legal risk, and available workarounds.

Testers may recommend a priority, but the final priority is normally agreed with the product owner, project manager, or development team.

---

## 2. Severity Levels

| Level | Meaning | Example |
|---|---|---|
| Critical | The system or a critical service is unavailable, or the defect causes severe data, security, or financial damage. | All users are unable to log in, or customer data is permanently deleted. |
| High | A core function is seriously affected, but the entire system is not unavailable. | The checkout total is calculated incorrectly. |
| Medium | A non-critical function is affected, and users may still complete the main task or use a workaround. | Product filtering returns incomplete results. |
| Low | The defect has a minor visual, text, or usability impact and does not block the main user flow. | A button color does not match the design specification. |

---

## 3. Priority Levels

| Level | Meaning | Example |
|---|---|---|
| Urgent | The defect requires immediate attention and may block a release or cause continuing harm. | Customers may be charged an incorrect amount during checkout. |
| High | The defect should be fixed in the current or next planned release. | Some users cannot complete payment. |
| Medium | The defect should be scheduled for correction but does not require immediate action. | A search filter produces incomplete results, but another search method is available. |
| Low | The defect can be fixed later without significant business or user impact. | Minor spacing or color inconsistency. |

---

## 4. Severity vs. Priority

| Question | Severity | Priority |
|---|---|---|
| What does it describe? | The seriousness of the impact | The urgency of the fix |
| Main focus | Users, data, security, money, and functionality | Release plans, deadlines, customers, and business needs |
| Key question | How serious is the consequence? | How soon should it be fixed? |
| Typical decision | Assessed by QA with the team | Agreed by product, project, development, and QA stakeholders |

Severity and priority are related, but they are not always the same.

### Example 1: High Severity and Urgent Priority

The checkout page displays an incorrect total and may charge customers the wrong amount.

- Severity: High
- Priority: Urgent
- Reason: It affects a core transaction and creates financial and customer-trust risks.

### Example 2: Low Severity and High Priority

The homepage displays the wrong date for a marketing campaign that begins tomorrow.

- Severity: Low
- Priority: High
- Reason: The functional impact is small, but the business deadline makes the correction urgent.

### Example 3: High Severity and Medium Priority

A rarely used internal administration page crashes, but administrators have a working alternative process.

- Severity: High
- Priority: Medium
- Reason: The failure is serious, but few users are affected and a workaround is available.

### Example 4: Low Severity and Low Priority

A secondary button uses a slightly incorrect color.

- Severity: Low
- Priority: Low
- Reason: The issue does not prevent users from completing any task.

---

## 5. Classification Checklist

Before assigning severity, check:

- Is a core function unavailable?
- Is user data lost or corrupted?
- Is money or security affected?
- How many users are affected?
- Can the user continue the task?
- Is a workaround available?

Before recommending priority, check:

- Does the issue block a release?
- Is there an upcoming deadline?
- Is the problem currently affecting customers?
- Is there legal, financial, or reputation risk?
- Is a workaround available?
- How expensive or risky is the fix?

---

## 6. Important Rules

1. Severity describes impact; priority describes urgency.
2. High severity does not automatically mean high priority.
3. A visual issue may have high priority when it affects an urgent campaign or important customer.
4. Do not assign severity based only on how surprising a defect looks.
5. Do not report an observation as a confirmed defect when the requirement is unclear.
6. Record the evidence and mark `Requirement needs confirmation` when necessary.
7. Severity and priority should include a short reason, not only a label.

---

## 7. Practical Example from This Portfolio

### Incorrect Shopping Cart Grand Total

Observed calculation:

- Product price: USD 45.00
- Quantity: 2
- Cart subtotal: USD 90.00
- Shipping: USD 7.99
- Expected grand total: USD 97.99
- Actual grand total: USD 197.99

Recommended classification:

- Severity: High
- Priority: Urgent

Reason:

The defect affects a core checkout calculation and may cause customers to see or pay an incorrect amount. It creates financial, conversion, and customer-trust risks and should be corrected before the checkout flow is released.

---

## 8. Severity and Priority Classification Exercise

| ID | Hypothetical Issue | Severity | Priority | Reason |
|---|---|---|---|---|
| SP-001 | All users are unable to log in. | Critical | Urgent | A core function is completely unavailable to every user, so access to the entire product is blocked. |
| SP-002 | Submitted customer data is permanently lost. | Critical | Urgent | The issue causes irreversible data loss and may create legal, operational, and customer-trust risks. |
| SP-003 | The shopping cart grand total is calculated incorrectly. | High | Urgent | A core checkout calculation is incorrect and customers may see or pay the wrong amount. |
| SP-004 | Some users cannot complete payment. | High | High | A revenue-generating function is blocked for affected users, although the entire system remains available. |
| SP-005 | Search results omit some matching products. | Medium | Medium | Search quality is affected, but users may still browse categories or use another method. |
| SP-006 | An error message is unclear, but the user can continue the task. | Medium | Medium | The message may confuse users and increase support requests, but it does not block the main flow. |
| SP-007 | A secondary button sometimes fails, but another working link is available. | Medium | Low | The function is affected, but a workaround is available and only a secondary flow is involved. |
| SP-008 | The homepage shows the wrong date for a campaign starting tomorrow. | Low | High | The technical impact is minor, but the approaching business deadline makes the correction urgent. |
| SP-009 | A page heading is slightly misaligned. | Low | Low | The issue is visual and does not prevent users from completing a task. |
| SP-010 | A button color does not match the approved design. | Low | Low | The issue has a minor visual impact and does not affect functionality. |
