# Executing Basic Queries

## Overview

In this lesson, we will learn how to execute basic SQL queries (SELECT, INSERT, UPDATE, DELETE) using the MySQL2 driver for Node.js. We will also cover handling query results and errors.

## Performing Basic Queries

To execute queries, you can use the `query` method provided by the MySQL2 driver. Here are examples of executing different types of queries:

### SELECT Query

```javascript
// select.js
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

### INSERT Query

```javascript
// insert.js
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
  const values = ['John Doe', 'john.doe@example.com']
  connection.query(sql, values, (err, results) => {
    if (err) {
      console.error('Error executing query:', err.stack)
      return
    }
    console.log('Insert results:', results)
  })

  connection.end()
})
```

### UPDATE Query

```javascript
// update.js
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
  const values = ['john.new@example.com', 'John Doe']
  connection.query(sql, values, (err, results) => {
    if (err) {
      console.error('Error executing query:', err.stack)
      return
    }
    console.log('Update results:', results)
  })

  connection.end()
})
```

### DELETE Query

```javascript
// delete.js
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
  const values = ['John Doe']
  connection.query(sql, values, (err, results) => {
    if (err) {
      console.error('Error executing query:', err.stack)
      return
    }
    console.log('Delete results:', results)
  })

  connection.end()
})
```

## Handling Query Results and Errors

When executing queries, it's important to handle results and errors appropriately. The examples above show how to process query results and handle potential errors using callbacks.

## Conclusion

In this lesson, we explored how to execute basic SQL queries using the MySQL2 driver for Node.js. We covered SELECT, INSERT, UPDATE, and DELETE queries and learned how to handle query results and errors. In the next lesson, we will delve into using prepared statements with MySQL2.

## Exercise

[Exercise: Executing Basic Queries](exercise.md)
