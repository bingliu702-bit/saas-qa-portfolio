
# Day 30 - API Test Scenarios

## Test Information

- Project: Order Management API (Hypothetical)
- Test Type: API Scenario Design
- Methods: GET, POST, PUT, PATCH, DELETE
- Scenario IDs: API-005 to API-014
- Total Scenarios: 10
- Execution Status: Not Run

## API-005 - Get a Nonexistent Order

- Method: GET
- Endpoint: /orders/999999
- Test Condition: Order ID 999999 does not exist.
- Expected Status Code: 404 Not Found
- Expected Result: The server returns 404 Not Found and does not return data belonging to another order.

## API-006 - Create a Valid Order

- Method: POST
- Endpoint: /orders
- Test Data:
```json
{
  "productId": 101,
  "quantity": 2
}
```
- Expected Status Code: 201 Created
- Expected Result: A new order is created. The response contains a new order ID, productId 101, and quantity 2.

## API-007 - Reject an Invalid Quantity

- Method: POST
- Endpoint: /orders
- Test Data:
```json
{
  "productId": 101,
  "quantity": 0
}
```
- Expected Status Code: 400 Bad Request
- Expected Result: The server rejects the invalid quantity and does not create a new order.

## API-008 - Update an Existing Order with PUT

- Method: PUT
- Endpoint: /orders/1001
- Test Condition: Order 1001 exists with productId 101 and quantity 2.
- Test Data:
```json
{
  "id": 1001,
  "productId": 101,
  "quantity": 5
}
```
- Expected Status Code: 200 OK
- Expected Result: The response contains id 1001, productId 101, and quantity 5. The existing order is updated.

## API-009 - Partially Update an Order with PATCH

- Method: PATCH
- Endpoint: /orders/1001
- Test Condition: Order 1001 exists with productId 101 and quantity 2.
- Test Data:
```json
{
  "quantity": 5
}
```
- Expected Status Code: 200 OK
- Expected Result: The response contains id 1001, productId 101, and quantity 5. Only the quantity changes; the other fields remain unchanged.

## API-010 - Delete an Existing Order

- Method: DELETE
- Endpoint: /orders/1001
- Request Body: None
- Test Condition: Order 1001 exists. At least one other order is available for an unaffected-record check.
- Expected Status Code: 204 No Content
- Expected Result: The DELETE response has an empty body. A subsequent GET /orders/1001 returns 404 Not Found. Other orders remain unaffected.

## API-011 - Reject an Unauthenticated Request

- Method: GET
- Endpoint: /orders/1001
- Test Condition: No Authorization header or other authentication credentials are provided.
- Expected Status Code: 401 Unauthorized
- Expected Result: The server rejects the unauthenticated request and does not expose order details.

## API-012 - Reject Unauthorized Order Access

- Method: GET
- Endpoint: /orders/1001
- Test Condition: User B uses a valid token to request order 1001, which belongs to User A.
- Expected Status Code: 403 Forbidden
- Expected Result: The server denies access and does not return User A's order details.

## API-013 - Reject a Duplicate Order Number

- Method: POST
- Endpoint: /orders
- Test Condition: An order with orderNumber ORD-1001 already exists. The client submits the same order number again.
- Test Data:
```json
{
  "orderNumber": "ORD-1001",
  "productId": 101,
  "quantity": 2
}
```
- Expected Status Code: 409 Conflict
- Expected Result: The server returns an error indicating that the order number already exists. No new order record is created.

## API-014 - Handle an Internal Server Error

- Method: GET
- Endpoint: /orders/1001
- Test Condition: Order ID 1001 exists, and the test environment simulates an internal server failure.
- Expected Status Code: 500 Internal Server Error
- Expected Result: The server returns an error response without exposing sensitive internal server information.

## Test Summary

- Total Scenarios: 10
- Scenario Design Review: Passed
- Execution Status: Not Run
- Actual Results: Not available
- Defects Found: Not assessed

## Notes

These scenarios are based on a hypothetical Order Management API. The expected status codes and behaviors are defined by the exercise specification, not verified against a live API.
  