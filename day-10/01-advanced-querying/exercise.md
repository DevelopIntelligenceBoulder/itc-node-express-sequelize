# Exercise: Advanced Querying with Sequelize

## Objective

Practice performing advanced queries using Sequelize to filter, sort, paginate, and execute complex queries on the `Post` model.

## Instructions

1. Use the Node.js project from the previous exercises.
2. Write scripts to perform advanced queries on the `Post` model.

## Steps

1. **Filter Posts**:
    - Create a `filter-posts.js` file.
    - Write code to filter posts by title.

2. **Sort Posts**:
    - Create a `sort-posts.js` file.
    - Write code to sort posts by title in ascending order.

3. **Paginate Posts**:
    - Create a `paginate-posts.js` file.
    - Write code to paginate posts with a limit of 2 and an offset of 1.

4. **Complex Query**:
    - Create a `complex-query.js` file.
    - Write code to filter posts by title using a wildcard, sort by title in ascending order, and paginate the results.

## Example Structure

### Filtering Posts

1. Filter posts where the title is 'First Post'.

### Sorting Posts

1. Sort posts by title in ascending order.

### Paginating Posts

1. Paginate posts with a limit of 2 and an offset of 1.

### Complex Query

1. Filter posts where the title contains 'Post'.
2. Sort the filtered posts by title in ascending order.
3. Paginate the results with a limit of 2 and an offset of 1.

4. **Run your scripts**:
    - Use the command `node filter-posts.js`, `node sort-posts.js`, `node paginate-posts.js`, and `node complex-query.js` to run your scripts and check the results.

Ensure your MySQL server is running and the database `test_db` exists. If you encounter any errors, troubleshoot based on the error messages and adjust your query logic or connection settings accordingly.
