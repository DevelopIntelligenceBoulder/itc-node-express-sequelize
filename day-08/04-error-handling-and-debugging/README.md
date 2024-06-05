# Error Handling and Debugging

## Overview

In this lesson, we will learn about error handling and debugging techniques when using the MySQL2 driver for Node.js. Proper error handling is crucial for building robust applications, and effective debugging helps identify and fix issues quickly.

## Common Errors

When working with the MySQL2 driver, you may encounter various errors such as connection errors, query errors, and validation errors. It's important to handle these errors gracefully and provide meaningful feedback to the user or logs.

### Example: Handling Connection Errors

```javascript
// connection-error.js
const mysql = require('mysql2')

const connection = mysql.createConnection({
  host: 'localhost',
  user: 'root',
  password: 'wrongpassword',
  database: 'test_db'
})

connection.connect((err) => {
  if (err) {
    console.error('Error connecting to the database:', err.message)
    // Additional error handling logic
    return
  }
  console.log('Connected to the database')
})
```

### Example: Handling Query Errors

```javascript
// query-error.js
const mysql = require('mysql2')

const connection = mysql.createConnection({
  host: 'localhost',
  user: 'root',
  password: 'password',
  database: 'test_db'
})

connection.connect((err) => {
  if (err) {
    console.error('Error connecting to the database:', err.message)
    return
  }
  console.log('Connected to the database')

  const sql = 'SELECT * FROM non_existing_table'
  connection.query(sql, (err, results) => {
    if (err) {
      console.error('Error executing query:', err.message)
      // Additional error handling logic
      return
    }
    console.log('Query results:', results)
  })

  connection.end()
})
```

## Debugging Techniques

Effective debugging is essential for identifying and fixing issues in your code. Here are some common debugging techniques:

### Using Console Logging

Console logging is a simple yet powerful technique for debugging. By logging variable values and execution flow, you can identify where things go wrong.

```javascript
// debug-logging.js
const mysql = require('mysql2')

const connection = mysql.createConnection({
  host: 'localhost',
  user: 'root',
  password: 'password',
  database: 'test_db'
})

connection.connect((err) => {
  if (err) {
    console.error('Error connecting to the database:', err.message)
    return
  }
  console.log('Connected to the database')

  const sql = 'SELECT * FROM users'
  console.log('Executing query:', sql)
  connection.query(sql, (err, results) => {
    if (err) {
      console.error('Error executing query:', err.message)
      return
    }
    console.log('Query results:', results)
  })

  connection.end()
})
```

### Using a Debugger

Using a debugger allows you to set breakpoints, inspect variables, and step through your code. Node.js can be debugged using various tools such as VS Code, WebStorm, and Chrome DevTools.

#### Example: Debugging with VS Code

1. Open your project in VS Code.
2. Set breakpoints by clicking in the gutter next to the line numbers.
3. Run the script in debug mode by selecting "Run" > "Start Debugging" or pressing `F5`.
4. Inspect variables and step through the code using the debug toolbar.

## Conclusion

In this lesson, we explored error handling and debugging techniques when using the MySQL2 driver for Node.js. We covered handling common errors, using console logging, and debugging with a debugger. In the next lesson, we will introduce Sequelize and compare it with using the MySQL2 driver.

## Exercise

[Exercise: Error Handling and Debugging](exercise.md)
