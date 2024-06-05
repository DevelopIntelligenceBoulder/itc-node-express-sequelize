# Exercise: Performing CRUD Operations with Sequelize

## Objective

Practice performing CRUD operations using Sequelize to manage records in a MySQL database.

## Instructions

1. Use the Node.js project from the previous exercises.
2. Write scripts to perform CRUD operations on the `Post` model.

## Steps

1. **Create a Post**:
    - Create a `create-post.js` file.
    - Write code to create a new post record.

2. **Read Posts**:
    - Create a `read-posts.js` file.
    - Write code to read all post records.

3. **Update a Post**:
    - Create an `update-post.js` file.
    - Write code to update a post's title by ID.

4. **Delete a Post**:
    - Create a `delete-post.js` file.
    - Write code to delete a post record by ID.

## Example Structure

### models/post.js

Define a `Post` model with the following attributes:
- `title`: string, not null
- `content`: text, not null

### create-post.js

1. Create a new Sequelize instance.
2. Import the `Post` model.
3. Synchronize the model with the database.
4. Create a new post with the following attributes:
    - `title`: 'First Post'
    - `content`: 'This is the content of the first post.'
5. Log the created post.

### read-posts.js

1. Create a new Sequelize instance.
2. Import the `Post` model.
3. Synchronize the model with the database.
4. Read all post records and log them.

### update-post.js

1. Create a new Sequelize instance.
2. Import the `Post` model.
3. Synchronize the model with the database.
4. Find a post by ID and update its title.
5. Log the updated post.

### delete-post.js

1. Create a new Sequelize instance.
2. Import the `Post` model.
3. Synchronize the model with the database.
4. Find a post by ID and delete the record.
5. Log a confirmation message.

4. **Run your scripts**:
    - Use the command `node create-post.js`, `node read-posts.js`, `node update-post.js`, and `node delete-post.js` to run your scripts and check the results.

Ensure your MySQL server is running and the database `test_db` exists. If you encounter any errors, troubleshoot based on the error messages and adjust your CRUD operations or connection settings accordingly.
