# Postman API Testing Project

This repository contains a collection of automated API tests for the [Automation Exercise](https://automationexercise.com/api) website using Postman. The project is designed to verify the correctness of API responses, including status codes, error handling, and response structures.

## Project Overview

The project consists of a Postman collection (`AutomationExerciseAPITests.postman_collection.json`) that includes several API tests. These tests validate that the API endpoints return the correct response codes and structures. The tests are automated using Newman, the command-line runner for Postman, which makes it easy to integrate into CI/CD pipelines.

## Key Features

- **Automated API testing:** Run tests on API endpoints and validate responses.
- **Error handling validation:** Ensure proper error responses and status codes.
- **Easy execution via Newman:** Use the included npm script to run tests with a single command.

## Prerequisites

Ensure that you have the following tools installed:

- [Node.js](https://nodejs.org/) (version 16 or higher)
- [Git](https://git-scm.com/) (for cloning the repository)

Newman is listed as a development dependency in the `package.json` file and will be installed automatically when you run `npm install`.

## Project Structure

- **`AutomationExerciseAPITests.postman_collection.json`**: The Postman collection containing all the API test cases.
- **`package.json`**: Configuration file listing the project’s dependencies and test scripts.
- **`package-lock.json`**: Automatically generated file to ensure consistent dependency versions across environments.

## Available API Tests

The following test cases are included in the Postman collection:

1. **All Products List**  
   Method: `GET`  
   URL: `/productsList`  
   Description: Retrieves a list of all products and checks for a successful response (`200` status code).

2. **All Products List Invalid Method**  
   Method: `POST`  
   URL: `/productsList`  
   Description: Tests an invalid request method (`POST`) and expects a `405` response code with the message: _"This request method is not supported."_.

3. **All Brands List**  
   Method: `GET`  
   URL: `/brandsList`  
   Description: Retrieves a list of all brands and ensures the response is valid (`200` status code).

4. **All Brands List Invalid Method**  
   Method: `PUT`  
   URL: `/brandsList`  
   Description: Tests an unsupported method (`PUT`) and expects a `405` response code with the appropriate error message.

5. **Search Product**  
   Method: `POST`  
   URL: `/searchProduct`  
   Description: Searches for products based on a search term and validates that the response contains a `products` array.

6. **Search Product Without Parameter**  
   Method: `POST`  
   URL: `/searchProduct`  
   Description: Attempts to search without providing the `search_product` parameter and expects a `400` response with the message: _"Bad request, search_product parameter is missing in POST request."_

7. **Verify Login Invalid Method**  
   Method: `DELETE`  
   URL: `/verifyLogin`  
   Description: Tests an unsupported request method (`DELETE`) and expects a `405` response code with the appropriate error message.

## Getting Started

Follow these steps to get started:

### 1. Clone the Repository

First, clone the repository to your local machine:

```bash
git clone https://github.com/kajus303/postman-api-testing-project.git
cd postman-api-testing-project
```

### 2. Install Dependencies

Install all required dependencies by running:

```bash
npm install
```

This command will automatically install Newman and any other required dependencies.

### 3. Running the Tests

You can run all the tests included in the Postman collection using the following command:

```bash
npm test
```

This will execute the `AutomationExerciseAPITests.postman_collection.json` using Newman and display the test results in the terminal.

### 4. Customizing the API Base URL

The base API URL is defined as a Postman environment variable `{{base_url}}`. You can modify the `base_url` in the collection or during runtime via Newman.
