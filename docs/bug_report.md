# Bug Report

## Bug-001: Non-existing resource API does not return detailed error message

### 1. Basic Information

* Bug ID: Bug-001
* Module: Post detail API
* Request name: GET non-existing post
* Method: GET
* Endpoint: `/posts/999999`
* Severity: Low
* Priority: P3
* Test environment: JSONPlaceholder public API
* Test tool: Postman / Newman

### 2. Description

When requesting a non-existing post resource, the API returns status code 404, but the response body is an empty object. The response does not contain a readable error message such as `post not found`.

### 3. Steps to Reproduce

1. Set `base_url` to `https://jsonplaceholder.typicode.com`.
2. Send a GET request to `/posts/999999`.
3. Check the response status code and response body.

### 4. Actual Result

* Status code: 404
* Response body:

```json
{}
```

### 5. Expected Result

The API should return status code 404 and provide a clear error message in the response body, for example:

```json
{
  "error": "post not found"
}
```

### 6. Impact

The client side cannot display a detailed error message to users. It also makes troubleshooting less convenient during API debugging.

### 7. Suggestion

Add a readable error message field in the response body when the requested resource does not exist.

### 8. Note

JSONPlaceholder is a public fake REST API. This bug report is recorded as an improvement suggestion for testing practice and portfolio demonstration.
