# Month 2 API Practice Collection

## 1. Purpose

This collection was created to practice and demonstrate fundamental API testing skills using Postman.

The practice covers HTTP methods, status codes, query parameters, request bodies, JSON responses, collection variables, and environment variables.

## 2. Base URL

The collection uses two public API services:

| Variable | Base URL |
|---|---|
| baseUrl | https://jsonplaceholder.typicode.com |
| echoBaseUrl | https://postman-echo.com |

Collection variables are used to reduce duplicate URL configuration and improve maintainability.

## 3. Folder Structure

The collection contains 13 API requests organized into four folders.

| Folder | Description | Requests |
|---|---|---|
| Users | User-related API requests | 2 |
| Posts | Post retrieval, creation, update, and deletion | 6 |
| Comments | Comment retrieval and filtering | 2 |
| HTTP Basics | Basic HTTP requests and query parameter validation | 3 |

## 4. How to Run

1. Open the collection in Postman.
2. Verify that both collection variables are configured correctly.
3. Select No Environment for normal API testing.
4. Open a request from the appropriate folder.
5. Click Send to execute the request.
6. Verify the status code and response body against the expected results.

The QA Practice environment is used to demonstrate that an environment variable takes precedence over a collection variable with the same name.

After completing the environment variable experiment, switch back to No Environment.

## 5. Known Limitations

- JSONPlaceholder is a simulated API. POST, PATCH, and DELETE responses do not represent persistent changes on the server.
- Postman Echo is used to practice HTTP requests and validate query parameters rather than real business functionality.
- Response times may vary depending on network conditions.
- The QA Practice environment is a variable precedence experiment, not a real QA server environment.
- Authentication, authorization, and automated assertions are not included in the current practice scope.

## 6. Tools and Test Approach

- Tool: Postman
- Test approach: Manual API testing
- HTTP methods: GET, POST, PATCH, DELETE
- Validation: Status codes, JSON response structures, field values, and query parameters.