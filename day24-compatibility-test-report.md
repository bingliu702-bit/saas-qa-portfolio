# Day 24 — Compatibility and Usability Test Report

## 1. Test Information

- **Project:** Stan Store Registration Page
- **URL:** https://admin.stan.store/register
- **Environment:** Windows 11, Google Chrome, Chrome DevTools
- **Viewport Sizes:** 1366×768, 375×667, 768×1024
- **Testing Types:** Compatibility Testing, Usability Testing
- **Device Type:** Simulated viewports (not physical devices)

## 2. Test Objective

Verify that the registration page displays correctly at different viewport sizes.

Check the page layout, scrolling behavior, and email error feedback.

## 3. Test Execution Summary

| Test ID | Test Item | Viewport | Status |
|---|---|---|---|
| CL-01 | Desktop Layout | 1366×768 | Passed |
| B2-1 | Mobile Scrolling | 375×667 | Passed |
| B3-1 | Tablet Layout | 768×1024 | Passed |
| B3-2 | Email Error Feedback | 768×1024 | Passed |
| SC-09 | Mobile Layout | 375×667 | Passed |
| SC-10 | Mobile Scrolling | 375×667 | Passed |
| SC-11 | Email Error Feedback | 768×1024 | Passed |

## 4. Test Scenarios

### SC-09 — Mobile Layout

**Environment:** Chrome DevTools, Responsive 375×667

**Expected Result:**

The registration page should display all main fields and the Next button clearly.

No elements should overlap or be obstructed.

**Actual Result:**

The Username, Full Name, Email, Phone Number, and Password fields and the Next button were fully visible.

No overlapping or obstruction was observed in the captured viewport.

**Status:** Passed

### SC-10 — Mobile Scrolling

**Environment:** Chrome DevTools, Responsive 375×667

**Expected Result:**

Users should be able to scroll to the bottom of the page.

All footer links should be fully visible without obstruction.

**Actual Result:**

The page could be scrolled to the bottom.

The Terms of Service, Privacy Policy, and Log in links were fully visible without obstruction.

**Status:** Passed

### SC-11 — Email Error Feedback

**Environment:** Chrome DevTools, Responsive 768×1024

**Test Data:** abc

**Expected Result:**

The system should display a clear and complete error message.

The message should be fully visible without obstruction and help the user understand that the email format is invalid.

**Actual Result:**

The Email field displayed a red border.

The system displayed an error message: "Please enter a valid email address."

The message was fully visible without obstruction.

**Status:** Passed

## 5. Defect Summary

No confirmed defects were found during the documented Day 24 checks.

This does not mean the registration page is free of defects.

## 6. Test Limitations

- Testing was performed using Chrome DevTools simulated viewports.
- No physical mobile or tablet devices were tested.
- Only the documented layout, scrolling, and error feedback checks were covered.
- Full browser compatibility testing was not performed.

## 7. Conclusion

The documented checks passed at the tested viewport sizes.

No confirmed defects were identified within the tested scope.

Additional testing would be required to assess other devices, browsers, and registration workflows.