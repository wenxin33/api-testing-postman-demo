# API Test Plan

## 1. Project Background

This project tests a public RESTful API service based on JSONPlaceholder. The purpose is to practice API test design, Postman test scripting, Newman command-line execution, HTML report generation, and test documentation.

The tested APIs are related to the `/posts` resource and cover common RESTful operations, including query, create, update, delete, and negative resource access.

## 2. Test Objectives

The objectives of this test project are:

1. Verify that the API can return expected status codes.
2. Verify that the response body contains required fields.
3. Verify that the response data matches the request data where applicable.
4. Verify that a non-existing resource returns a proper error status code.
5. Verify that the API response time is within a basic acceptable range.
6. Verify that the Postman Collection can be executed through Newman.
7. Generate an HTML test report for result review.

## 3. Test Scope

### 3.1 In Scope

The following APIs are included in this test project:

| Method | Endpoint      | Description           |
| ------ | ------------- | --------------------- |
| GET    | /posts        | Get posts list        |
| GET    | /posts/1      | Get post detail       |
| GET    | /posts/999999 | Get non-existing post |
| POST   | /posts        | Create a post         |
| PUT    | /posts/1      | Update a post         |
| DELETE | /posts/1      | Delete a post         |

### 3.2 Out of Scope

The following test types are not included:

* Authentication testing
* Authorization testing
* Database persistence verification
* Security testing
* Load testing
* Complex business workflow testing

## 4. Test Types

This project includes the following test types:

1. Functional testing
2. Negative testing
3. Status code validation
4. Response body validation
5. Business field validation
6. Basic response time validation

## 5. Test Tools

| Tool                 | Purpose                                  |
| -------------------- | ---------------------------------------- |
| Postman              | Create and debug API requests            |
| Newman               | Run Postman Collection from command line |
| Node.js              | Provide runtime environment for Newman   |
| newman-reporter-html | Generate HTML test report                |
| Git / GitHub         | Manage and publish the project           |

## 6. Test Environment

* Operating system: Windows
* API base URL: `https://jsonplaceholder.typicode.com`
* Test tool: Postman
* Command-line runner: Newman
* Report format: HTML

## 7. Pass Criteria

The test is considered passed if:

1. All six API requests can be executed successfully.
2. All Postman test scripts pass.
3. Newman can run the exported Collection successfully.
4. The number of failed requests is 0.
5. The number of failed assertions is 0.
6. The HTML test report is generated successfully.

## 8. Risk and Limitation

JSONPlaceholder is a public fake REST API. POST, PUT, and DELETE requests return simulated responses but do not persist data. Therefore, this project focuses on API request validation, response validation, and testing workflow demonstration rather than real business data verification.

The response time assertion uses a 3000 ms threshold because public API response time may vary due to network conditions.
