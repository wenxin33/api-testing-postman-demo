# API Testing Postman Demo

## 1. Project Overview

This project is an API testing portfolio project based on Postman and Newman. The tested service is JSONPlaceholder, a public RESTful API commonly used for testing and prototyping.

The project covers common RESTful API testing scenarios, including list query, detail query, negative resource query, resource creation, resource update, and resource deletion.

This project is designed to demonstrate basic API testing ability, Postman test scripting, Newman command-line execution, HTML test report generation, and test documentation.

## 2. Tech Stack

* Postman
* Newman
* Node.js
* RESTful API
* JavaScript test scripts
* HTML test report
* Git / GitHub

## 3. Tested API

Base URL:

```text
https://jsonplaceholder.typicode.com
```

| No. | Request Name          | Method | Endpoint      | Test Focus                                   |
| --- | --------------------- | ------ | ------------- | -------------------------------------------- |
| 1   | GET posts list        | GET    | /posts        | List query, response array, required fields  |
| 2   | GET post detail       | GET    | /posts/1      | Detail query, id validation, required fields |
| 3   | GET non-existing post | GET    | /posts/999999 | Negative resource test, 404 response         |
| 4   | POST create post      | POST   | /posts        | Resource creation, 201 status, response data |
| 5   | PUT update post       | PUT    | /posts/1      | Resource update, response field validation   |
| 6   | DELETE post           | DELETE | /posts/1      | Resource deletion, 200 status                |

## 4. Project Structure

```text
api-testing-postman-demo/
├── README.md
├── docs/
│   ├── test_plan.md
│   ├── test_cases.md
│   ├── bug_report.md
│   └── test_summary_report.md
├── postman/
│   ├── jsonplaceholder_api_test.postman_collection.json
│   └── jsonplaceholder_env.postman_environment.json
└── reports/
    └── newman_report.html
```

## 5. How to Run

Install Newman:

```bash
npm install -g newman
```

Run the Postman collection:

```bash
newman run "postman\jsonplaceholder_api_test.postman_collection.json" -e "postman\jsonplaceholder_env.postman_environment.json"
```

Generate HTML report:

```bash
npm install -g newman-reporter-html

newman run "postman\jsonplaceholder_api_test.postman_collection.json" -e "postman\jsonplaceholder_env.postman_environment.json" -r cli,html --reporter-html-export "reports\newman_report.html"
```

If the exported environment value is empty, the base URL can also be passed directly:

```bash
newman run "postman\jsonplaceholder_api_test.postman_collection.json" --env-var "base_url=https://jsonplaceholder.typicode.com"
```

## 6. Test Result

The current test collection includes:

* Total requests: 6
* Total assertions: 16
* Failed requests: 0
* Failed assertions: 0
* HTML report: `reports/newman_report.html`

## 7. Test Coverage

This project covers:

* Status code validation
* Response field validation
* Business data validation
* Negative test case validation
* Basic response time validation
* Newman command-line execution
* HTML report generation

## 8. Documents

* [Test Plan](docs/test_plan.md)
* [Test Cases](docs/test_cases.md)
* [Bug Report](docs/bug_report.md)
* [Test Summary Report](docs/test_summary_report.md)

## 9. Notes

JSONPlaceholder is a fake online REST API. POST, PUT, and DELETE requests return simulated responses but do not actually persist data on the server.

The response time assertion is set to 3000 ms because this project uses a public API, and network delay may vary across different environments.
