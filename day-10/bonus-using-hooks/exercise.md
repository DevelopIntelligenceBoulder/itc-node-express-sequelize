# Exercise: Using Hooks with Sequelize

## Objective

Practice using hooks in Sequelize to execute custom logic before and after creating and updating records.

## Instructions

1. Use the Node.js project from the previous exercises.
2. Write scripts to define hooks in the `Post` model and attach hooks to a model instance.

## Steps

1. **Define hooks in the `Post` model**:
    - Modify the `models/post.js` file to include `beforeCreate` and `afterCreate` hooks.
    - Log a message before and after creating a post.

2. **Attach hooks to the `Post` model instance**:
    - Create an `attach-hooks.js` file.
    - Attach a `beforeUpdate` hook to the `Post` model.
    - Log a message before updating a post.

3. **Create and update a post**:
    - Write code to create a new post.
    - Update the title of the post.
    - Verify that the hooks are executed correctly by checking the logged messages.

## Example Structure

### Defining Hooks in the `Post` Model

1. Add `beforeCreate` and `afterCreate` hooks to log messages.

### Attaching Hooks to the `Post` Model Instance

1. Attach a `beforeUpdate` hook to log a message before updating a post.

### Creating and Updating a Post

1. Create a new post and update its title.
2. Verify that the hooks are executed by checking the logged messages.

4. **Run your scripts**:
    - Use the command `node attach-hooks.js` to run your script and check the results.

Ensure your MySQL server is running and the database `test_db` exists. If you encounter any errors, troubleshoot based on the error messages and adjust your hook logic or connection settings accordingly.
