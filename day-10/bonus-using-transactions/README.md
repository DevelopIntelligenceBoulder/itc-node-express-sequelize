# Using Transactions with Sequelize

## Overview

In this lesson, we will learn how to use transactions in Sequelize. Transactions allow you to execute a series of operations as a single unit of work, ensuring data integrity. If any operation in the transaction fails, all changes can be rolled back to maintain a consistent state.

## What are Transactions?

Transactions are used to ensure that a series of database operations are executed atomically. This means that either all operations succeed, or none of them do, ensuring that the database remains in a consistent state.

## Using Transactions

To use transactions in Sequelize, you can use the `transaction` method. This method starts a new transaction, and you can pass the transaction object to your queries to ensure they are executed within the transaction.

### Example: Using Transactions

```javascript
// transaction-example.js
const { Sequelize, DataTypes } = require('sequelize')
const sequelize = new Sequelize('test_db', 'root', 'password', {
  host: 'localhost',
  dialect: 'mysql'
})

const User = sequelize.define('User', {
  name: {
    type: DataTypes.STRING,
    allowNull: false
  },
  email: {
    type: DataTypes.STRING,
    allowNull: false,
    unique: true
  }
})

const Post = sequelize.define('Post', {
  title: {
    type: DataTypes.STRING,
    allowNull: false
  },
  content: {
    type: DataTypes.TEXT,
    allowNull: false
  }
})

User.hasMany(Post)
Post.belongsTo(User)

async function createUserAndPosts() {
  const transaction = await sequelize.transaction()

  try {
    const user = await User.create({ name: 'John Doe', email: 'john.doe@example.com' }, { transaction })
    await Post.create({ title: 'First Post', content: 'This is my first post!', userId: user.id }, { transaction })

    await transaction.commit()
    console.log('Transaction committed successfully.')
  } catch (error) {
    await transaction.rollback()
    console.error('Transaction rolled back due to an error:', error)
  } finally {
    await sequelize.close()
  }
}

createUserAndPosts()
```

## Conclusion

In this lesson, we explored how to use transactions in Sequelize. We learned how to start a transaction, execute queries within the transaction, and handle commit and rollback operations. Transactions are crucial for ensuring data integrity in your applications. 

## Exercise

[Exercise: Using Transactions with Sequelize](exercise.md)
