# Day 14 - Week 2 Review

## Part A: Technical Knowledge Review

### Q1. What happens when a user clicks the Login button?

When a user clicks the Login button, the browser sends an HTTP request to the server.

The server processes the request and checks the submitted credentials.

The server then sends an HTTP response back to the browser.

Depending on the response, the browser may display a success message, show an error, or redirect the user to another page.

**Example from Day 11:**
- `POST /authenticate` - 303 See Other
- `GET /secure` - 200 OK

This indicates that the login request was followed by a redirect to the secure area.

### Q2. What is the purpose of the Console panel? Does every red error mean a website bug?

The Console panel is used to inspect JavaScript errors, warnings, and debugging messages.

Not every red error indicates a confirmed website bug.

Some errors may come from browser extensions or third-party services.

A QA tester should investigate the error, check whether it affects functionality, and collect reproducible evidence before reporting a bug.

### Q3. What is the purpose of the Network panel? What do HTTP status codes 200, 302, and 303 mean?

The Network panel is used to inspect HTTP requests and responses between the browser and the server.

It helps testers check request URLs, HTTP methods, status codes, headers, and response times.

**Common HTTP status codes:**

- **200 OK:** The request was successful.
- **302 Found:** The server temporarily redirects the browser to another URL.
- **303 See Other:** The server redirects the client to another URL, typically using a GET request.

**Example from Day 11:**

`POST /authenticate` → `303` → `GET /secure` → `200`

A successful HTTP response does not always mean that the entire business function works correctly.

### Q4. What are Cookies and Local Storage? What is the difference?

Cookies and Local Storage are browser storage mechanisms.

**Cookies:**
- Can store session identifiers and user preferences.
- Are automatically included in matching HTTP requests, depending on cookie settings.
- May expire based on their configuration.

**Local Storage:**
- Stores data locally in the browser.
- Is not automatically sent with HTTP requests.
- Usually persists until the data is cleared.

**Key difference:**

Cookies can be automatically sent to the server with matching requests, while Local Storage data is not automatically sent.

### Q5. Why should a Bug Report include Expected Result, Actual Result, and Evidence?

A Bug Report should clearly describe what was expected, what actually happened, and what evidence supports the observation.

- **Expected Result:** Describes how the system should behave.
- **Actual Result:** Describes what happened during testing.
- **Evidence:** Includes screenshots, recordings, logs, or Network details that support the findings.

These fields help developers and other testers understand, reproduce, and investigate the issue.

**Example (hypothetical):**

**Title:** Login button does not respond after clicking.

**Steps to Reproduce:**
1. Open the login page.
2. Enter valid credentials.
3. Click the Login button.

**Expected Result:** The user should be redirected to the secure area.

**Actual Result:** The page remains on the login screen.

**Evidence:** Screenshot and Network request details.

*Note: This is an example for practicing Bug Report structure, not a confirmed defect.*

---

## Key Terms Review

| Term | Meaning |
|---|---|
| Request | A message sent from the browser to the server |
| Response | A message returned by the server |
| Console | A tool for inspecting errors, warnings, and debugging messages |
| Network | A tool for inspecting HTTP requests and responses |
| Cookie | Browser-stored data that can be sent with matching HTTP requests |
| Local Storage | Browser-stored data that is not automatically sent with HTTP requests |
| Expected Result | What should happen |
| Actual Result | What actually happened |
| Evidence | Information supporting the test findings |

## Review Status

- Review type: Guided review using reference answers
- Topics reviewed: HTTP, Console, Network, Cookies, Local Storage, and Bug Reports
- Independent recall: Not yet assessed
- Next task: Review existing Bug Reports and test scenarios

## Bug Report Review

Three existing bug reports were reviewed:

- BR-001: Incorrect Grand Total Displayed in Shopping Cart
- BR-002: Currency Selection Triggers a Crash Overlay and Fails to Convert Prices
- BR-003: Russian Text Is Displayed on the English Login Page

No additional confirmed defects were identified during the subsequent testing activities.

The testing activities included form validation, browser Console inspection, Network request analysis, browser storage observation, and responsive layout testing.

Test scenarios, actual observations, and supporting evidence were documented where applicable.

**Review Result:** Three existing bug reports reviewed. No new bug reports created.

**Lesson Learned:** A test can provide useful evidence even when no defect is found. A failed test or unusual observation should not automatically be classified as a confirmed bug.

## Part G: Independent Test Scenario Design

I independently designed five login test scenarios within the review exercise:

1. Login with valid credentials.
2. Login with a valid username and an empty password.
3. Login with an empty username and a valid password.
4. Login with an invalid username.
5. Login with a valid username and an incorrect password.

**Review Result:** Passed the basic scenario design exercise.

**Self-Assessment:**

I can identify common positive and negative login test scenarios and describe basic test steps.

I need to improve the precision of expected results and use more specific test data.

**Next Improvement Goal:**

Write clear, measurable, and verifiable expected results instead of general descriptions such as "the page should work normally."

**Note:** These five scenarios were designed and reviewed but were not executed as part of this exercise.