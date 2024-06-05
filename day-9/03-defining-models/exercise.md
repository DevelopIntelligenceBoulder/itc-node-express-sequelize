# Exercise: Defining Models with Sequelize

## Objective

Practice defining models in Sequelize, setting up associations, and adding validation. Verify the models by creating and querying sample data.

## Instructions

1. Use the Node.js project from the previous exercises.
2. Write scripts to define models, set up associations, add validation, and verify the models by creating and querying sample data.

## Steps

1. **Define a `User` model**:
    - Create a `models/user.js` file.
    - Define the `User` model with the following attributes:
        - `name`: string, not null
        - `email`: string, not null, unique

2. **Define a `Post` model**:
    - Create a `models/post.js` file.
    - Define the `Post` model with the following attributes:
        - `title`: string, not null
        - `content`: text, not null

3. **Set up associations**:
    - In the `models/post.js` file, define the following associations:
        - A `User` has many `Post`s.
        - A `Post` belongs to a `User`.

4. **Add validation to the `User` model**:
    - Add validation rules to ensure the `name` is not empty and the `email` is a valid email address.

5. **Sync the models with the database and create sample data**:
    - Write a script to sync the models with the database.
    - Create a sample user and some posts associated with that user.
    - Query and log the created data to verify the models.

## Example Code

### sync-and-test.js

```javascript
const { Sequelize } = require('sequelize')
const sequelize = new Sequelize('test_db', 'root', 'password', {
  host: 'localhost',
  dialect: 'mysql'
})

const User = require('./models/user')
const Post = require('./models/post')

async function syncAndTest() {
  try {
    await sequelize.sync({ force: true }) // This will drop and recreate the tables
    console.log('Models synchronized successfully.')

    const user = await User.create({ name: 'John Doe', email: 'john.doe@example.com' })
    console.log('User created:', user.toJSON())

    const post = await Post.create({ title: 'First Post', content: 'This is my first post!', userId: user.id })
    console.log('Post created:', post.toJSON())

    const posts = await User.findOne({ where: { id: user.id }, include: Post })
    console.log('User with posts:', JSON.stringify(posts, null, 2))
  } catch (error) {
    console.error('Error syncing or testing models:', error)
  } finally {
    await sequelize.close()
  }
}

syncAndTest()
```

4. **Run your scripts**:
    - Use the command `node sync-and-test.js` to run your script and check the results.

Ensure your MySQL server is running and the database `test_db` exists. If you encounter any errors, troubleshoot based on the error messages and adjust your model definitions or connection settings accordingly.
