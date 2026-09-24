# BR-003: Russian Text Is Displayed on the English Login Page

## Summary

A Russian instruction is displayed in the **New User** section of the English login page opened through the **Dark Blue Denim Jeans** product.

The rest of the page is displayed in English, resulting in an inconsistent user interface language.

## Environment

* **Starting URL:** https://academybugs.com/find-bugs/
* **Test date:** September 24, 2026
* **Browser:** Google Chrome 153.0.8010.53
* **Operating system:** Windows 11
* **Tester:** bingliu702-bit
* **Page language:** English

## Preconditions

1. The AcademyBugs website is available.
2. The user is signed out.
3. Browser translation is disabled.
4. The test starts from the **Find Bugs** page.

## Steps to Reproduce

1. Open the AcademyBugs **Find Bugs** page.
2. Find and open **Dark Blue Denim Jeans**.
3. Click **Login for Pricing**.
4. Observe the instruction displayed under the **New User** heading.

## Expected Result

All text on the English login page should be displayed in English.

For example, the instruction should read:

`Not registered? Click the button below.`

## Actual Result

The following instruction is displayed in Russian:

`Не зарегистрированы? Нажмите кнопку ниже`

Other labels and instructions on the page are displayed in English.

## Reproduction Rate

**3/3 attempts**

The Russian text was displayed during all three independent attempts.

## Severity

**Low**

The issue creates a language inconsistency and may confuse users who do not understand Russian. However, the **Create Account** button and an additional English explanation remain available, so the registration flow is not blocked.

## Priority Recommendation

**Low**

The untranslated text should be corrected as part of localization and content-quality improvements, but it does not prevent users from signing in or creating an account.

> Priority is a recommendation and should be confirmed by the product owner or project manager.

## Status

**Open**

## Evidence

<img width="1806" height="932" alt="3e3ea380-1c9c-4aa9-bfbc-05a96634d6d0" src="https://github.com/user-attachments/assets/6ec1e862-64e6-4496-8f59-1772b68b0217" />

The screenshot shows:

* The page interface displayed in English
* The **New User** section
* The Russian instruction
* The **Create Account** button
* The English explanation displayed below the Russian instruction

## Additional Notes

The browser translation feature was disabled when the evidence was captured. The issue appears to be a page-content localization defect rather than a browser translation problem.
