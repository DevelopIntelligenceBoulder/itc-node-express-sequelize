# Connecting to a MySQL Database with Sequelize

## Overview

In this lesson, we will learn how to establish a connection to a MySQL database using Sequelize. We will explore the configuration options and how to test the connection.

## Establishing a Connection

To connect to a MySQL database using Sequelize, you need to create an instance of Sequelize with the appropriate configuration. 

### Example

```javascript
// sequelize-connection.js
const { Sequelize } = require('sequelize')

const sequelize = new Sequelize('test_db', 'root', 'password', {
  host: 'localhost',
  dialect: 'mysql'
})

async function testConnection() {
  try {
    await sequelize.authenticate()
    console.log('Connection has been established successfully.')
  } catch (error) {
    console.error('Unable to connect to the database:', error)
  }
}

testConnection()
```

## Configuration Options

Sequelize provides various configuration options to customize the connection. Here are some commonly used options:

- **host**: The hostname of the database you are connecting to.
- **dialect**: The SQL dialect of the database (e.g., 'mysql', 'postgres', 'sqlite', 'mssql').
- **pool**: Connection pool configuration.
  - **max**: Maximum number of connections in the pool.
  - **min**: Minimum number of connections in the pool.
  - **idle**: The maximum time, in milliseconds, that a connection can be idle before being released.
  - **acquire**: The maximum time, in milliseconds, that pool will try to get a connection before throwing an error.

### Example with Pool Configuration

```javascript
const sequelize = new Sequelize('test_db', 'root', 'password', {
  host: 'localhost',
  dialect: 'mysql',
  pool: {
    max: 5,
    min: 0,
    idle: 10000,
    acquire: 30000
  }
})

async function testConnection() {
  try {
    await sequelize.authenticate()
    console.log('Connection has been established successfully.')
  } catch (error) {
    console.error('Unable to connect to the database:', error)
  }
}

testConnection()
```

## Conclusion

In this lesson, we explored how to establish a connection to a MySQL database using Sequelize. We covered the basic configuration and additional options for connection pooling. In the next lesson, we will learn how to define models using Sequelize.

## Exercise

[Exercise: Connecting to a MySQL Database with Sequelize](exercise.md)
