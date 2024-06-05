# Exercise: Enhance Error Handling in Express

## Objective
Develop advanced error handling mechanisms in your Express application to manage different types of errors effectively and improve application robustness.

## Task
Expand your Express server's error-handling capabilities to include detailed and appropriate responses for different error scenarios, including both client-side and server-side errors.

## Instructions
1. **Setup Your Project**:
   - If you don't already have an Express application, set up a basic one with a few routes.
   - Include at least one route that could potentially lead to a server error (e.g., by throwing an exception).

2. **Implement Error Handling**:
   - Design and implement middleware to catch 404 (Not Found) errors for unspecified routes.
   - Create error-handling middleware to manage 500 (Internal Server Error) for any server-side issues.
   - Ensure that the error handling provides clear, user-friendly error messages and logs the errors for debugging purposes.

3. **Requirements for Error Messages**:
   - **404 Errors**: Provide a custom message indicating that the requested resource was not found.
   - **500 Errors**: Give a generic error message to the client and ensure detailed error information is logged on the server.

4. **Testing Your Error Handling**:
   - Deliberately access non-existent routes to trigger 404 errors.
   - Trigger a 500 error by accessing a route designed to fail.
   - Observe and verify that the responses and logs are as expected.

## Expected Output
- Custom error messages for 404 and 500 errors.
- Detailed error logging for server-side issues, visible only on the server.
