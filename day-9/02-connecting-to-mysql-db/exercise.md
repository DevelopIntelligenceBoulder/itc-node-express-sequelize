# Exercise: Connecting to a MySQL Database with Sequelize

## Objective

Practice establishing a connection to a MySQL database using Sequelize with various configuration options.

## Instructions

1. Use the Node.js project from the previous exercises.
2. Write a script to create a Sequelize instance and test the connection with different configurations.

## Steps

1. **Create a Sequelize connection script**:
    - Create a `sequelize-connection.js` file.
    - Write code to create a Sequelize instance with the following configuration:
        - Database: `test_db`
        - User: `root`
        - Password: `password`
        - Host: `localhost`
        - Dialect: `mysql`

2. **Test the connection**:
    - Write a function to authenticate the Sequelize instance and log the result.

3. **Add pool configuration**:
    - Modify the Sequelize instance to include a connection pool with the following configuration:
        - Max connections: 5
        - Min connections: 0
        - Idle time: 10000 ms
        - Acquire time: 30000 ms

4. **Run your script**:
    - Use the command `node sequelize-connection.js` to run your script and check the connection status.

Ensure your MySQL server is running and the database `test_db` exists. If you encounter any errors, troubleshoot based on the error messages and adjust your connection settings accordingly.
