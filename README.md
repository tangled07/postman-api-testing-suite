# Automated REST API Testing Suite

## Overview

This project demonstrates automated REST API testing using Postman, JavaScript test scripts, and JSONPlaceholder, a public practice REST API. The project focuses on validating HTTP responses, checking data quality, testing error handling, and verifying consistency across endpoints.

I created a collection of six API requests with ten automated test assertions to practice validating API behavior and data reliability.

## Objectives

- Validate HTTP status codes and expected API responses.
- Verify response fields, data types, and required values.
- Test filtered results and invalid endpoints.
- Validate POST request behavior and returned data.
- Check response time against a defined threshold.
- Verify consistency between different API endpoints.
- Use data-driven testing to validate requested post IDs.

## Tools and Technologies

- **Postman:** Creating requests and running automated tests.
- **JavaScript:** Writing test scripts and assertions.
- **JSONPlaceholder:** Providing a public practice REST API.
- **JSON:** Supplying iteration data for data-driven testing.
- **GitHub:** Hosting project files and documentation.

## Project Structure

```text
postman-api-testing-suite/
├── README.md
├── postman/
│   └── Automated REST API Testing Suite.postman_collection.json
└── test-data/
    └── post-test-data.json
```

## API Test Scenarios

### 1. GET Valid Post

**Endpoint:** `GET /posts/1`

Validates that an individual post can be retrieved successfully.

Assertions:
- Status code is 200.
- Response contains the expected post.
- Post data has valid fields.
- Response time is under 1000 milliseconds.

### 2. GET Filtered Data

**Endpoint:** `GET /posts?userId=1`

Validates that the API returns posts belonging to the specified user.

Assertions:
- Status code is 200.
- All returned posts belong to user 1.

### 3. GET Invalid Endpoint

**Endpoint:** `GET /invalid-endpoint`

Validates that the API handles an invalid endpoint as expected.

Assertion:
- Invalid endpoint returns status code 404.

### 4. POST

**Endpoint:** `POST /posts`

Validates the API's response to a request to create a post.

Assertions:
- Status code is 201.
- Response contains the submitted post.
- Response contains a generated ID.

### 5. GET Cross-Endpoint

**Endpoint:** `GET /posts`

Validates consistency between the post returned by the individual-post endpoint and the post included in the full posts collection.

Assertion:
- Post 1 is consistent across endpoints.

The test uses collection variables to compare the saved post data with the corresponding post returned by the collection endpoint.

### 6. GET Data Driven

**Endpoint:** `GET /posts/{{postId}}`

Validates individual posts using a reusable request and test script.

Assertion:
- Response matches the requested post ID.

The `postId` variable is supplied through a JSON iteration data file when the request is run using Postman's Collection Runner.

## How to Run the Tests

1. Install [Postman](https://www.postman.com/downloads/).
2. Download or clone this repository.
3. Import `jsonplaceholder-api-tests.postman_collection.json` into Postman.
4. Run the regular requests or the collection without iteration data.
5. To run the data-driven test, select the `GET Data Driven` request or its dedicated folder in Collection Runner.
6. Import `post-test-data.json` as the iteration data file.
7. Run the test and review the results for each iteration.

**Important:** The data-driven test requires iteration data because the request URL uses the `postId` variable. Run it with the JSON file configured in Collection Runner.

## Results

All ten automated assertions passed during testing across the six API requests.

The tests covered successful responses, response data validation, filtering, invalid endpoint handling, simulated resource creation, response-time validation, cross-endpoint consistency, and data-driven testing.

## Limitations

JSONPlaceholder is a practice API rather than a production backend. POST requests simulate resource creation and do not permanently store new data. The one-second response-time threshold is a practice benchmark and does not guarantee production performance.

## Learning Outcomes

This project strengthened my understanding of REST APIs, HTTP status codes, JavaScript assertions, response validation, collection variables, and data-driven testing.

It also helped me understand how automated tests can validate expected behavior and data consistency across endpoints. These concepts are relevant to backend software engineering, where testing helps identify issues and improve the reliability of services.

## Future Improvements

- Add negative test cases for invalid request bodies and parameters.
- Explore authentication and authorization testing.
- Validate responses against a formal API schema.
- Integrate automated tests into a CI/CD pipeline.

