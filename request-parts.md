# Day 31 - HTTP Request Parts

## 1. Parameters

### 1.1 Path Parameter

A Path Parameter identifies a specific resource in the URL path.

Example:
`GET /posts/15`

- Parameter name: `id`
- Parameter value: `15`
- Purpose: Retrieve the post with ID 15.

### 1.2 Query Parameter

A Query Parameter provides filtering or querying conditions after `?` in the URL.

Example:
`GET /posts?userId=999`

- Parameter name: `userId`
- Parameter value: `999`
- Purpose: Retrieve posts belonging to user 999.

### 1.3 Key Difference

- Path Parameters identify resources in the URL path.
- Query Parameters provide query conditions after `?`.

## 2. HTTP Headers

HTTP Headers provide additional information about an HTTP request or response.

### 2.1 Content-Type

`Content-Type` describes the media type of the request body.

Example:

```http
POST /posts
Content-Type: application/json
```

This means the request body is sent in JSON format.

### 2.2 Accept

`Accept` indicates the response media types the client can accept.

Example:

```http
GET /posts/1
Accept: application/json
```

This means the client requests a JSON response.

### 2.3 Key Difference

- `Content-Type`: Describes the format of the data being sent.
- `Accept`: Indicates the preferred format of the response.
- The actual response must still be verified by the QA tester.

## 3. Request Body and JSON Data Types

### 3.1 Request Body

A Request Body contains data sent from the client to the server.

Example:

```http
POST /posts
Content-Type: application/json
```

```json
{
  "title": "QA Learning",
  "body": "Learning API Testing",
  "userId": 3,
  "published": false
}
```

### 3.2 JSON Data Types

| Field | Value | JSON Type |
|---|---|---|
| title | "QA Learning" | String |
| body | "Learning API Testing" | String |
| userId | 3 | Number |
| published | false | Boolean |

### 3.3 Important Differences

- `"3"` is a String, while `3` is a Number.
- `"false"` is a String, while `false` is a Boolean.
- The Request Body contains data sent by the client.
- The Response Body contains data returned by the server.
- Response fields and values must be verified against the API requirements.

## 4. API Test Examples

### 4.1 GET - Filtering

Request:

```http
GET /posts?userId=1
```

Expected Result:

- HTTP Status: 200 OK
- Response Body: JSON Array
- Every returned post has `userId = 1`.
- Each post contains the required fields: `userId`, `id`, `title`, and `body`.

### 4.2 POST - Create a Post

Request:

```http
POST /posts
Content-Type: application/json
```

Request Body:

```json
{
  "title": "API Testing Practice",
  "body": "Learning Postman API testing",
  "userId": 3
}
```

Expected Result:

- HTTP Status: 201 Created
- Response Body: JSON Object
- `title`, `body`, and `userId` match the submitted values.
- The response contains a simulated resource `id` of type Number.

Note: JSONPlaceholder simulates creation and does not persist the new post.

### 4.3 PATCH - Partial Update

Request:

```http
PATCH /posts/1
Content-Type: application/json
```

Request Body:

```json
{
  "title": "Updated QA Title Day 31"
}
```

Expected Result:

- HTTP Status: 200 OK
- Response Body: JSON Object
- The `title` field matches the updated value.
- The `id` remains 1.
- Other fields remain unchanged compared with the verified baseline.

Note: This is a simulated update. Unchanged fields must be checked against the original response.

### 4.4 Empty Result

Request:

```http
GET /posts?userId=999
```

Expected Result:

- HTTP Status: 200 OK
- Response Body: JSON Array
- Expected Body: `[]`
- Expected Record Count: 0

## 5. API Testing Checklist

- Verify the HTTP status code.
- Verify the JSON response structure.
- Verify required fields and data types.
- Verify field values against expected results.
- Do not assume success from the status code alone.
- Distinguish simulated API responses from persistent database changes.