# Exercise: Error Handling and Debugging

## Objective

Practice error handling and debugging techniques using the MySQL2 driver for Node.js.

## Instructions

1. Use the Node.js project from the previous exercises.
2. Write scripts to handle different types of errors and use debugging techniques.

## Steps

1. **Create a script to handle connection errors**:
    - Create a `connection-error.js` file.
    - Write code to handle connection errors.

2. **Create a script to handle query errors**:
    - Create a `query-error.js` file.
    - Write code to handle query errors.

3. **Create a script to use console logging for debugging**:
    - Create a `debug-logging.js` file.
    - Write code to use console logging for debugging.

4. **Optional: Debug using VS Code**:
    - Open your project in VS Code.
    - Set breakpoints in your code.
    - Run the script in debug mode and inspect variables.

## Example Structure

### Handling Connection Errors

* Create a connection to the database with incorrect credentials.
* Log the error message if the connection fails.

### Handling Query Errors

* Create a connection to the database with correct credentials.
* Execute a query on a non-existing table.
* Log the error message if the query fails.

### Using Console Logging for Debugging

* Create a connection to the database with correct credentials.
* Log the SQL query being executed.
* Log the results of the query.
* Handle and log any errors that occur during the connection or query execution.

4. **Run your scripts**:
    - Use the command `node connection-error.js`, `node query-error.js`, and `node debug-logging.js` to run your scripts and check the results.

Ensure your MySQL server is running and the database `test_db` exists with a `users` table. If you encounter any errors, troubleshoot based on the error messages and adjust your connection settings accordingly.
