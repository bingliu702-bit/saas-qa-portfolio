# Day 32 — JSON Reading & API Response Validation

## 1. Test Information

- Project: JSONPlaceholder API Testing
- Tool: Postman
- Test Type: Manual API Testing
- Environment: Windows 11
- Execution Date: 2026-11-24

## 2. Objective

Verify JSON response structures, field paths, values, data types, and query parameter filtering results.

## 3. API Requests

| ID | HTTP Method | Endpoint |
|---|---|---|
| API-01 | GET | /users/1 |
| API-02 | GET | /users |
| API-03 | GET | /posts/1 |
| API-04 | GET | /posts?userId=1 |
| API-05 | GET | /comments?postId=1 |

Base URL: https://jsonplaceholder.typicode.com

## 4. JSON Field Reading — 10 Exercises

| ID | API | Target Field | Field Path | Actual Value | Data Type |
|---|---|---|---|---|---|
| JR-01 | API-01 | User ID | `id` | `1` | Number |
| JR-02 | API-01 | Address city | `address.city` | `"Gwenborough"` | String |
| JR-03 | API-01 | Geo latitude | `address.geo.lat` | `"-37.3159"` | String |
| JR-04 | API-02 | Second user's username | `[1].username` | `"Antonette"` | String |
| JR-05 | API-02 | Third user's company name | `[2].company.name` | `"Romaguera-Jacobson"` | String |
| JR-06 | API-03 | Article userId | `userId` | `1` | Number |
| JR-07 | API-03 | Article title | `title` | `"sunt aut facere repellat provident occaecati excepturi optio reprehenderit"` | String |
| JR-08 | API-04 | First article ID | `[0].id` | `1` | Number |
| JR-09 | API-04 | Last article ID | `[9].id` | `10` | Number |
| JR-10 | API-05 | First comment's postId | `[0].postId` | `1` | Number |

## 5. Query Parameter Validation

### Test Case 1 — Filter Posts by userId

- Request: GET /posts?userId=1
- Expected Result: All returned posts have userId = 1.
- Actual Result: The API returned 10 posts. All 10 posts had userId = 1.
- Test Result: Passed.

### Test Case 2 — Filter Comments by postId

- Request: GET /comments?postId=1
- Expected Result: All returned comments have postId = 1.
- Actual Result: The API returned 5 comments. All 5 comments had postId = 1.
- Test Result: Passed.

## 6. Findings and Limitations

- Check that JSON field paths match the actual response structure.
- Distinguish resource IDs from array indices.
- Confirm data types before evaluating field values.
- Filtering consistency alone does not establish that all expected records were returned.

## 7. Conclusion

During Day 32, five API endpoints were tested using Postman.

Ten JSON field-reading exercises were documented, covering objects, arrays, nested structures, field paths, values, and data types.

Two query parameter filtering checks were completed. All 10 returned posts had userId = 1, and all 5 returned comments had postId = 1. Both filtering consistency checks passed.

These results demonstrate that the returned records matched the specified filter conditions. However, the tests did not independently verify whether all expected records were returned.

No filtering inconsistencies were observed in the tested responses.
