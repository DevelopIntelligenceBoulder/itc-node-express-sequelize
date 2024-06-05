# Exercise: Using Transactions with Sequelize

## Objective

Practice using transactions in Sequelize to ensure data integrity when performing a series of operations.

## Instructions

1. Use the Node.js project from the previous exercises.
2. Define the necessary models and their relationships.
3. Write a script to perform a series of operations within a transaction.
4. Ensure the script handles both commit and rollback scenarios, including intentional error handling.

## Steps

1. **Define Models**:
    - Create a `models/user.js` file and define the `User` model with the following attributes:
        - `name`: string, not null
        - `email`: string, not null, unique
    - Create a `models/post.js` file and define the `Post` model with the following attributes:
        - `title`: string, not null
        - `content`: text, not null
    - Ensure that a `User` has many `Post`s and a `Post` belongs to a `User`.

2. **Set Up Sequelize and Synchronize Models**:
    - Create a `sequelize-setup.js` file.
    - Import Sequelize and the models.
    - Set up a Sequelize connection and synchronize the models with the database.

3. **Create a Transaction Script**:
    - Create a `transaction-example.js` file.
    - Import the Sequelize connection and the models.
    - Write code to start a transaction.
    - Within the transaction, create a new user and at least two associated posts.
    - Introduce an intentional error (e.g., trying to create a post with a missing required field) to test the rollback functionality.
    - Commit the transaction if all operations succeed.
    - Roll back the transaction if any operation fails.

4. **Verify Transaction Behavior**:
    - Log messages to indicate whether the transaction was committed or rolled back.
    - Verify that the database remains in a consistent state after the transaction.

## Example Structure

### Defining Models

1. Define a `User` model with attributes `name` and `email`.
2. Define a `Post` model with attributes `title` and `content`.
3. Ensure the `User` and `Post` models have the correct associations.

### Setting Up Sequelize

1. Create a `sequelize-setup.js` file.
2. Import Sequelize and the models.
3. Set up a Sequelize connection.
4. Synchronize the models with the database.

### Creating a Transaction Script

1. Create a `transaction-example.js` file.
2. Import the Sequelize connection and the models.
3. Write code to start a transaction.
4. Create a new user and at least two associated posts within the transaction.
5. Introduce an intentional error to test rollback.
6. Commit the transaction if all operations succeed.
7. Roll back the transaction if any operation fails.

4. **Run your script**:
    - Use the command `node transaction-example.js` to run your script and check the results.

Ensure your MySQL server is running and the database `test_db` exists. If you encounter any errors, troubleshoot based on the error messages and adjust your transaction logic or connection settings accordingly.
