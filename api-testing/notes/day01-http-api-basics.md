# Day 01 - HTTP & API Basics

## Project Information
- Project: Postman Echo API Testing
- Tool: Postman
- Test Type: Manual API Testing

## Test Execution Records

### API-001: Basic GET Request

- Request URL: https://postman-echo.com/get
- Method: GET
- Expected Result: The server should return HTTP 200 OK and a JSON response containing an empty args object.
- Actual Result: The server returned HTTP 200 OK and a JSON response containing an empty args object.
- Status Code: 200 OK
- Response Time: 825 ms
- Response Body Type: JSON
- Test Result: Passed

### API-002: GET Request with Query Parameters

- Request URL: https://postman-echo.com/get?product=book&quantity=2
- Method: GET
- Expected Result: The server should return HTTP 200 OK and a JSON response containing an `args` object with `product = "book"` and `quantity = "2"`.
- Actual Result: The server returned HTTP 200 OK and a JSON response containing an `args` object with `product = "book"` and `quantity = "2"`.
- Status Code: 200 OK
- Response Time: 859 ms
- Response Body Type: JSON
- Test Result:Passed

### API-003: GET Request with Three Query Parameters

- Request URL: https://postman-echo.com/get?category=electronics&page=2&limit=10
- Method: GET
- Expected Result: The server should return HTTP 200 OK and a JSON response containing an `args` object with `category = "electronics"` and `page = "2"`and `limit = "10"`.
- Actual Result: The server returned HTTP 200 OK and a JSON response containing an `args` object with `category = "electronics"` and `page = "2"`and `limit = "10"`.
- Status Code: 200 OK
- Response Time: 1150 ms
- Response Body Type: JSON
- Test Result:Passed

## API Terminology

## API Terminology

1. **Client:** A client sends requests to a server and receives responses.

2. **Server:** A server receives requests, processes them, and sends responses.

3. **Request:** A request is a message sent by a client to a server.

4. **Response:** A response is a message sent by a server back to a client.

5. **Endpoint:** An endpoint is a specific URL where a client can access an API resource or operation.