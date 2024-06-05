# Using Hooks with Sequelize

## Overview

In this lesson, we will learn how to use hooks in Sequelize. Hooks are functions that can be executed before or after certain events, such as creating, updating, or deleting records. They are useful for tasks like validation, logging, and modifying data.

## What are Hooks?

Hooks are also known as lifecycle events or callbacks. Sequelize provides various hooks that you can use to execute code at different points in the lifecycle of a model instance.

### Common Hooks

- `beforeValidate`
- `afterValidate`
- `beforeCreate`
- `afterCreate`
- `beforeUpdate`
- `afterUpdate`
- `beforeDestroy`
- `afterDestroy`

## Using Hooks

To use hooks, you can define them in your model or attach them to your model instance. Here is an example of defining hooks in a model:

### Example: Using Hooks in a Model

```javascript
// models/post.js
const { Sequelize, DataTypes } = require('sequelize')
const sequelize = new Sequelize('test_db', 'root', 'password', {
  host: 'localhost',
  dialect: 'mysql'
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
}, {
  hooks: {
    beforeCreate: (post, options) => {
      console.log('Before creating a post:', post)
    },
    afterCreate: (post, options) => {
      console.log('After creating a post:', post)
    }
  }
})

module.exports = Post
```

### Example: Attaching Hooks to Model Instance

```javascript
// attach-hooks.js
const { Sequelize } = require('sequelize')
const sequelize = new Sequelize('test_db', 'root', 'password', {
  host: 'localhost',
  dialect: 'mysql'
})

const Post = require('./models/post')

Post.addHook('beforeUpdate', (post, options) => {
  console.log('Before updating a post:', post)
})

async function createAndUpdatePost() {
  await sequelize.sync()

  const post = await Post.create({ title: 'First Post', content: 'This is my first post!' })
  console.log('Post created:', post.toJSON())

  post.title = 'Updated Post Title'
  await post.save()
  console.log('Post updated:', post.toJSON())

  await sequelize.close()
}

createAndUpdatePost()
```

## Conclusion

In this lesson, we explored how to use hooks in Sequelize. We covered defining hooks in a model and attaching hooks to a model instance. Hooks are powerful tools for executing custom logic at various points in the lifecycle of your model instances. 

## Exercise

[Exercise: Using Hooks with Sequelize](exercise.md)
