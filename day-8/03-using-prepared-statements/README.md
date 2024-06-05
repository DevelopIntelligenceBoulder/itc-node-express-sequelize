# Using Prepared Statements

## Overview

In this lesson, we will learn about prepared statements and how to use them with the MySQL2 driver for Node.js. Prepared statements offer security and performance benefits, especially when executing queries with user input.

## What are Prepared Statements?

Prepared statements are precompiled SQL statements that can be executed multiple times with different parameters. They help prevent SQL injection attacks and can improve performance by reusing the execution plan.

## Benefits of Prepared Statements

1. **Security**: Prevents SQL injection by separating SQL logic from data.
2. **Performance**: Reuses the execution plan for repeated queries, reducing overhead.
3. **Convenience**: Simplifies code when working with dynamic data.

## Using Prepared Statements with MySQL2

To use prepared statements, you can use the `execute` method provided by the MySQL2 driver. Here are examples of using prepared statements for different types of queries:

### SELECT Query with Prepared Statement

```javascript
// select-prepared.js
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

### INSERT Query with Prepared Statement

```javascript
// insert-prepared.js
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

  const sql = 'INSERT INTO users (name, email) VALUES (?, ?)'
  const values = ['Jane Doe', 'jane.doe@example.com']
  connection.execute(sql, values, (err, results) => {
    if (err) {
      console.error('Error executing query:', err.stack)
      return
    }
    console.log('Insert results:', results)
  })

  connection.end()
})
```

### UPDATE Query with Prepared Statement

```javascript
// update-prepared.js
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

  const sql = 'UPDATE users SET email = ? WHERE name = ?'
  const values = ['jane.new@example.com', 'Jane Doe']
  connection.execute(sql, values, (err, results) => {
    if (err) {
      console.error('Error executing query:', err.stack)
      return
    }
    console.log('Update results:', results)
  })

  connection.end()
})
```

### DELETE Query with Prepared Statement

```javascript
// delete-prepared.js
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

  const sql = 'DELETE FROM users WHERE name = ?'
  const values = ['Jane Doe']
  connection.execute(sql, values, (err, results) => {
    if (err) {
      console.error('Error executing query:', err.stack)
      return
    }
    console.log('Delete results:', results)
  })

  connection.end()
})
```

## Conclusion

In this lesson, we explored how to use prepared statements with the MySQL2 driver for Node.js. We covered the benefits of prepared statements and provided examples of using them for SELECT, INSERT, UPDATE, and DELETE queries. In the next lesson, we will learn about managing connections and using connection pooling with MySQL2.

## Exercise

[Exercise: Using Prepared Statements](exercise.md)
