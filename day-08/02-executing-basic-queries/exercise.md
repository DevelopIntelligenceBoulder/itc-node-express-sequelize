# Exercise: Executing Basic Queries

## Objective

Practice executing basic SQL queries (SELECT, INSERT, UPDATE, DELETE) using the MySQL2 driver for Node.js and handling query results and errors.

## Instructions

1. Use the Node.js project from the previous exercises.
2. Write scripts to execute basic SQL queries and handle results and errors.

## Steps

1. **Create a SELECT query script**:
    - Create a `select.js` file.
    - Write code to execute a SELECT query and display the results.

2. **Create an INSERT query script**:
    - Create an `insert.js` file.
    - Write code to execute an INSERT query and display the results.

3. **Create an UPDATE query script**:
    - Create an `update.js` file.
    - Write code to execute an UPDATE query and display the results.

4. **Create a DELETE query script**:
    - Create a `delete.js` file.
    - Write code to execute a DELETE query and display the results.

## Example Code

### SELECT Query

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

  const sql = 'SELECT * FROM users'
  connection.query(sql, (err, results) => {
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
    - Use the command `node select.js`, `node insert.js`, `node update.js`, and `node delete.js` to run your scripts and check the results.

Ensure your MySQL server is running and the database `test_db` exists with a `users` table. If you encounter any errors, troubleshoot based on the error messages and adjust your queries or connection settings accordingly.
