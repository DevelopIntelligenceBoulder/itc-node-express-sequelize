# Introduction to the MySQL2 Driver

## Overview

The MySQL2 driver for Node.js allows you to connect to a MySQL database from your Node.js application, execute queries, and handle results. This lesson introduces the MySQL2 driver, its installation, setup process, and reasons for choosing MySQL2 over the original MySQL driver.

## What is the MySQL2 Driver?

The MySQL2 driver for Node.js is a modern, optimized library that enables interaction with a MySQL database. It offers several improvements over the original MySQL driver, including better performance, support for Promises, and native prepared statements.

### Why Use MySQL2 Instead of MySQL?

1. **Performance**: MySQL2 is generally faster and more efficient than the original MySQL driver.
2. **Promises**: MySQL2 has built-in support for Promises, making it easier to use with modern JavaScript features like async/await.
3. **Prepared Statements**: MySQL2 supports native prepared statements, enhancing security and performance.
4. **Compatibility**: MySQL2 is fully backward compatible with MySQL, making the transition seamless.

## Installation and Setup

To use the MySQL2 driver, you need to install it using npm:

```bash
npm install mysql2
```

After installing the driver, you can set up your Node.js project to use it. Here’s a basic example:

### Example Setup

1. **Create a new Node.js project**:

```bash
mkdir mysql2-demo
cd mysql2-demo
npm init -y
```

2. **Install the MySQL2 driver**:

```bash
npm install mysql2
```

3. **Create a connection to the MySQL database**:

```javascript
// index.js
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
})
```

4. **Run your script**:

```bash
node index.js
```

If the connection is successful, you should see a message indicating that you are connected to the database.

## Conclusion

In this lesson, you learned what the MySQL2 driver is, why it is preferred over the original MySQL driver, how to install it, and set up a basic connection to a MySQL database.

## Exercise

[Exercise: Introduction to MySQL2 Driver](exercise.md)
