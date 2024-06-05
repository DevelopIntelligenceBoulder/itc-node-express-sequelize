# Exercise: Using Prepared Statements

## Objective

Practice using prepared statements with the MySQL2 driver for Node.js to execute various types of SQL queries securely and efficiently.

## Instructions

1. Use the Node.js project from the previous exercises.
2. Write scripts to execute SQL queries using prepared statements.

## Steps

1. **Create a SELECT query script with prepared statements**:
    - Create a `select-prepared.js` file.
    - Write code to execute a SELECT query using a prepared statement.

2. **Create an INSERT query script with prepared statements**:
    - Create an `insert-prepared.js` file.
    - Write code to execute an INSERT query using a prepared statement.

3. **Create an UPDATE query script with prepared statements**:
    - Create an `update-prepared.js` file.
    - Write code to execute an UPDATE query using a prepared statement.

4. **Create a DELETE query script with prepared statements**:
    - Create a `delete-prepared.js` file.
    - Write code to execute a DELETE query using a prepared statement.

## Example Code

### SELECT Query with Prepared Statement

```javascript
const mysql = require('mysql2')

const connection = mysql.createConnection({
  host: 'localhost',
  user: 'root',
  password: 'password',
  database: 'test_db'
})

connection.connect((err) => {
  if (err) {
    console.error('Error connecting to the database:', err.stack)
    return
  }
  console.log('Connected to the database')

  const sql = 'SELECT * FROM users WHERE email = ?'
  const values = ['john.doe@example.com']
  connection.execute(sql, values, (err, results) => {
    if (err) {
      console.error('Error executing query:', err.stack)
      return
    }
    console.log('Query results:', results)
  })

  connection.end()
})
```

4. **Run your scripts**:
    - Use the command `node select-prepared.js`, `node insert-prepared.js`, `node update-prepared.js`, and `node delete-prepared.js` to run your scripts and check the results.

Ensure your MySQL server is running and the database `test_db` exists with a `users` table. If you encounter any errors, troubleshoot based on the error messages and adjust your queries or connection settings accordingly.
