# Test Summary Report

## 1. Test Overview

This project completed API testing for JSONPlaceholder `/posts` related endpoints. The tests were designed and executed using Postman, and command-line execution was completed using Newman.

The project covers common RESTful API operations, including list query, detail query, negative resource query, resource creation, resource update, and resource deletion.

## 2. Test Scope

The tested APIs include:

| No. | Method | Endpoint        | Description           |
| --- | ------ | --------------- | --------------------- |
| 1   | GET    | `/posts`        | Get posts list        |
| 2   | GET    | `/posts/1`      | Get post detail       |
| 3   | GET    | `/posts/999999` | Get non-existing post |
| 4   | POST   | `/posts`        | Create a post         |
| 5   | PUT    | `/posts/1`      | Update a post         |
| 6   | DELETE | `/posts/1`      | Delete a post         |

## 3. Test Environment

* Operating system: Windows
* Test tool: Postman
* Command-line runner: Newman
* Runtime: Node.js
* Report tool: newman-reporter-html
* API base URL: `https://jsonplaceholder.typicode.com`

## 4. Test Result

| Item              | Result                       |
| ----------------- | ---------------------------- |
| Total iterations  | 1                            |
| Total requests    | 6                            |
| Failed requests   | 0                            |
| Test scripts      | 6                            |
| Total assertions  | 16                           |
| Failed assertions | 0                            |
| HTML report       | `reports/newman_report.html` |

## 5. Test Coverage

This test project covers:

1. Status code validation
2. Response body structure validation
3. Business field validation
4. Negative resource validation
5. Basic response time validation
6. Newman command-line execution
7. HTML test report generation

## 6. Issues Found

One improvement suggestion was recorded:

* `GET /posts/999999` returns status code 404 but does not provide a detailed error message in the response body.

This issue is not a blocking defect because JSONPlaceholder is a fake public API, but it is useful as a bug report example for testing practice.

## 7. Risk and Limitation

JSONPlaceholder is a fake online REST API. POST, PUT, and DELETE requests return simulated responses but do not actually persist data on the server.

The response time assertion is set to 3000 ms because the tested API is public and network delay may vary across different environments. This project does not include formal performance testing.

## 8. Conclusion

All designed API test cases were executed successfully. The Newman command-line run completed with 6 requests and 16 assertions, with 0 failed requests and 0 failed assertions.

This project demonstrates basic API test design, Postman assertion scripting, Newman command-line execution, HTML report generation, and test documentation ability.
