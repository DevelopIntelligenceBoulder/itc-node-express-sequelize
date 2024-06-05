# Exercise: Introduction to MySQL2 Driver

## Objective

Get familiar with the MySQL2 driver for Node.js by setting up a new project, installing the driver, and establishing a connection to a MySQL database.

## Instructions

1. Create a new Node.js project.
2. Install the MySQL2 driver using npm.
3. Write a script to connect to a MySQL database.

## Steps

1. **Create a new Node.js project**:
    - Use the command line to create a new directory for your project.
    - Initialize a new Node.js project using `npm init -y`.

2. **Install the MySQL2 driver**:
    - Use the command `npm install mysql2` to install the MySQL2 driver.

3. **Write a connection script**:
    - Create an `index.js` file.
    - Write code to establish a connection to a MySQL database. Use the following credentials (or adjust them to match your database setup):
        - Host: `localhost`
        - User: `root`
        - Password: `password`
        - Database: `test_db`

4. **Run your script**:
    - Use the command `node index.js` to run your script and check the connection status.

## Example Code

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
})
```

Ensure your MySQL server is running and the database `test_db` exists. If you encounter any errors, troubleshoot based on the error messages and adjust your connection settings accordingly.
