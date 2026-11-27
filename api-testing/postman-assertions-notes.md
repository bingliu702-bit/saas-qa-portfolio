
# Postman Assertions – API Testing Practice

## 1. Objective

The objective of this practice is to validate API responses using
Postman test scripts and identify mismatches between actual and
expected results.

## 2. Test Environment

- Operating System: Windows 11
- Testing Tool: Postman Web
- API: JSONPlaceholder
- Base URL: https://jsonplaceholder.typicode.com
- Collection: Month 2 API Practice
- Environment: No Environment
- Test Approach: Scripted API Response Validation

## 3. Core Assertion Concepts

| Method | Purpose |
|---|---|
| pm.test() | Defines a named test and records its result. |
| pm.expect() | Creates an expectation for actual data. |
| pm.response.json() | Parses the response body as JSON data. |
| to.have.status() | Validates the HTTP status code. |
| to.equal() | Checks strict equality. |
| to.be.a() | Validates the data type. |
| to.include() | Checks whether a value contains expected content. |
| to.have.property() | Checks whether a property exists. |

## 4. Assertion Examples

### 4.1 Status Code Assertion

```javascript
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```

Risk covered: Unexpected HTTP response status.

### 4.2 Content-Type Assertion

```javascript
pm.test("Content-Type is JSON", function () {
    pm.expect(pm.response.headers.get("Content-Type"))
        .to.include("application/json");
});
```

Risk covered: Unexpected response media type.

### 4.3 JSON Field Value Assertion

```javascript
pm.test("Post ID is 1", function () {
    const jsonData = pm.response.json();
    pm.expect(jsonData.id).to.equal(1);
});
```

Risk covered: Incorrect resource identification.

### 4.4 JSON Field Type Assertion

```javascript
pm.test("Email is a string", function () {
    const jsonData = pm.response.json();
    pm.expect(jsonData.email).to.be.a("string");
});
```

Risk covered: Incorrect data type or missing field.

This assertion was practiced before the final assertion coverage
was adjusted.

## 5. Final Assertion Coverage

| ID | Request | Expected Result | Risk Covered | Result |
|---|---|---|---|---|
| AT-001 | GET /posts/1 | Status 200 | Unexpected HTTP status | Passed |
| AT-002 | GET /posts/1 | Content-Type includes application/json | Unexpected media type | Passed |
| AT-003 | GET /posts/1 | id equals 1 | Incorrect post returned | Passed |
| AT-004 | GET /users/1 | Status 200 | Unexpected HTTP status | Passed |
| AT-005 | GET /users/1 | Content-Type includes application/json | Unexpected media type | Passed |
| AT-006 | GET /users/1 | id equals 1 | Incorrect user returned | Passed |
| AT-007 | POST /posts | Status 201 | Unexpected creation response | Passed |
| AT-008 | POST /posts | Content-Type includes application/json | Unexpected media type | Passed |
| AT-009 | POST /posts | title equals QA Testing | Incorrect response data | Passed |
| AT-010 | PATCH /posts/15 | Status 200 | Unexpected update response | Passed |
| AT-011 | PATCH /posts/15 | Content-Type includes application/json | Unexpected media type | Passed |
| AT-012 | PATCH /posts/15 | title equals Updated Title | Incorrect updated value | Passed |

## 6. Intentional Assertion Failure

Request: PATCH /posts/15

The expected title was intentionally changed from
"Updated Title" to "Wrong Title".

```javascript
pm.expect(jsonData.title).to.equal("Wrong Title");
```

Execution result:

- HTTP Status: 200 OK
- Passed Assertions: 2
- Failed Assertions: 1

Error message:

```text
AssertionError: expected 'Updated Title' to equal 'Wrong Title'
```

### Root Cause

The assertion failed because the expected value was
intentionally configured incorrectly.

This was a test script issue, not an API defect.

### Resolution

The expected value was restored to "Updated Title".

```javascript
pm.expect(jsonData.title).to.equal("Updated Title");
```

After re-execution, all three assertions passed.

## 7. Common Mistakes and Troubleshooting

| Issue | Corrective Action |
|---|---|
| Incorrect expected value | Verify the business requirement. |
| Incorrect JSON field path | Inspect the actual response structure. |
| Case-sensitive field names | Match the exact JSON property name. |
| Inconsistent variable names | Check variable declarations and references. |
| Missing quotation marks or brackets | Review JavaScript syntax. |
| Incorrect request selection | Verify the method and endpoint before execution. |
| Misleading test names | Ensure the test name matches the assertion logic. |
| Unsaved script changes | Save the request after verification. |

## 8. Test Execution Summary

| Metric | Result |
|---|---|
| Requests Tested | 4 |
| Final Assertions | 12 |
| Passed Assertions | 12 |
| Failed Assertions in Final Runs | 0 |
| Intentional Failure Simulations | 1 |
| Recovery Verification | Passed |

The results were collected from individual request executions,
not a single Collection Runner execution.

## 9. Test Limitations

- Passing assertions do not prove that the API is defect-free.
- Only selected response properties were validated.
- Content-Type validation alone does not guarantee valid JSON.
- Full response schema validation was not performed.
- Authentication and authorization were outside the test scope.
- JSONPlaceholder simulates resource creation and updates.
- Permanent database changes were not verified.
- A successful PATCH response does not prove that all other
  fields remained unchanged.

## 10. Key Takeaways

- HTTP success does not guarantee test success.
- An assertion failure does not automatically indicate an API defect.
- Expected results must be based on business requirements.
- Test names must accurately describe assertion logic.
- The correct request and endpoint must be verified before testing.
- Assertions should cover meaningful business risks.
