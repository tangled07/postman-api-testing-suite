# Automated REST API Testing Suite

## Overview

This project demonstrates API testing using Postman, JavaScript test scripts, and JSONPlaceholder, a public practice REST API. The purpose of the project is to validate API responses, verify data quality, test expected HTTP status codes, and automate repeatable tests.

## Objectives

- Test REST API endpoints using HTTP requests.
- Validate response status codes and response data.
- Check required fields and data types.
- Test expected behavior for invalid endpoints.
- Validate POST request responses.
- Measure response time against a defined threshold.
- Verify data consistency across endpoints.
- Use data-driven testing to validate multiple post IDs.

## Tools and Technologies

- **Postman:** Creating API requests and running automated tests.
- **JavaScript:** Writing assertions to validate API responses.
- **JSONPlaceholder:** Providing a practice REST API for testing.
- **GitHub:** Storing and documenting the project.

## Test Scenarios

| Test Scenario | Purpose |
|---|---|
| Retrieve a single post | Verify a successful response and expected post data. |
| Retrieve posts by user ID | Validate that returned posts match the requested user ID. |
| Request an invalid endpoint | Verify that the API returns the expected 404 status code. |
| Submit a POST request | Validate the response status and returned post fields. |
| Validate response data | Check field types and ensure required text fields are not empty. |
| Check response time | Confirm the response is below the configured one-second threshold. |
| Verify data consistency | Compare post data returned by different endpoints. |
| Data-driven testing | Validate multiple post IDs using an imported JSON iteration data file. |

## Project Structure

```text
postman-api-testing-suite/
├── README.md
├── postman/
│   └── jsonplaceholder-api-tests.postman_collection.json
└── test-data/
    └── post-test-data.json
```

The project also includes screenshots of the test results in the accompanying assignment document.

## How to Run the Tests

1. Install [Postman](https://www.postman.com/downloads/).
2. Clone or download this repository.
3. Open Postman and import the exported collection JSON file.
4. Open the imported collection to review the requests and test scripts.
5. Run the collection using Postman's Collection Runner.
6. To run the data-driven test, select the relevant request or folder in Collection Runner and import `post-test-data.json` as the iteration data file.
7. Review the results to confirm which tests passed or failed.

**Note:** The data-driven request uses the `{{postId}}` variable supplied by the iteration data file. Run it through Collection Runner with the JSON file configured to provide the required values.

## Results

The automated tests passed during my final test runs, including the data-driven test when executed with its imported iteration data.

The suite validates API response status codes, response fields, data types, expected error behavior, response-time requirements, and consistency across endpoints.

## Limitations

JSONPlaceholder is a practice API rather than a production backend. POST requests simulate resource creation and do not permanently store new data. The one-second response-time threshold is a practice benchmark and does not guarantee production performance.

## Learning Outcomes

This project strengthened my understanding of REST APIs, HTTP status codes, JavaScript assertions, response validation, collection variables, and automated test execution.

The skills developed through this project are relevant to backend software engineering because automated API tests help verify that services return expected data and behave consistently.

## Future Improvements

- Add more negative test cases and input validation scenarios.
- Explore authentication and authorization testing.
- Validate API responses against a formal schema.
- Integrate automated tests into a CI/CD pipeline.
