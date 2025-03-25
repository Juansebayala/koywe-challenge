# Testing

## Why

Testing is crucial for maintaining code quality and ensuring reliable functionality. In our application, we focus on both unit tests and integration tests to validate individual components and their interactions. Unit tests verify the behavior of isolated components like services and facades, while integration tests ensure that different parts of the system work together correctly. This dual approach helps us catch issues early and maintain a robust codebase.

## How

We use Jest as our testing framework. For unit tests, we mock dependencies to isolate the component being tested, allowing us to verify specific behaviors and error handling scenarios. Integration tests, on the other hand, test the interaction between multiple components, such as controllers, services, and repositories, providing confidence that our application's features work as expected.When working with databases we mock our repositories to simulate database operations. This approach allows us to test our business logic without the complexity of a real database connection, while still ensuring our code interacts correctly with the data layer.When working with external services, like APIs, we mock the specific code that is in charge of communicating with these external services or we can even spin up a mock server with test data that emulates the real service.
npm run test

```
# Runs all unit and integration tests once.

npm run test:watch

# Runs all tests in watch mode, re-running tests when files change.

npm run test:cov

# Runs all tests once and generates a coverage report in ./coverage.

npm run test:debug

# Runs tests in debug mode with Node.js inspector enabled for debugging.

```
