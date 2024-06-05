# Exercise: Introduction to Sequelize

## Objective

Get familiar with Sequelize by setting up a new project, installing Sequelize and the MySQL2 driver, and establishing a connection to a MySQL database.

## Instructions

1. Create a new Node.js project.
2. Install Sequelize and the MySQL2 driver using npm.
3. Write a script to create a Sequelize instance and test the connection to a MySQL database.

## Steps

1. **Create a new Node.js project**:
    - Use the command line to create a new directory for your project.
    - Initialize a new Node.js project using `npm init -y`.

2. **Install Sequelize and the MySQL2 driver**:
    - Use the command `npm install sequelize mysql2` to install Sequelize and the MySQL2 driver.

3. **Write a Sequelize setup script**:
    - Create a `sequelize-setup.js` file.
    - Write code to create a Sequelize instance with the following configuration:
        - Database: `test_db`
        - User: `root`
        - Password: `password`
        - Host: `localhost`
        - Dialect: `mysql`

4. **Test the connection**:
    - Write a function to authenticate the Sequelize instance and log the result.
    - Run your script to test the connection.

Ensure your MySQL server is running and the database `test_db` exists. If you encounter any errors, troubleshoot based on the error messages and adjust your connection settings accordingly.
