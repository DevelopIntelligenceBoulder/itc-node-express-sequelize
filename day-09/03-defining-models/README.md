### Defining Models with Sequelize

## Overview

In this lesson, we will learn how to define models in Sequelize. Models represent tables in your database and allow you to interact with the data in a structured way. We will cover how to define models, set up associations, and add validation.

## What are Models?

Models in Sequelize are JavaScript classes that represent tables in your database. Each model corresponds to a table and defines the structure of the table, including the columns and their data types.

## Defining a Model

To define a model, use the `sequelize.define` method or extend the `Model` class. Here is an example of defining a `User` model:

### Example

```javascript
// models/user.js
const { Sequelize, DataTypes } = require('sequelize')
const sequelize = new Sequelize('test_db', 'root', 'password', {
  host: 'localhost',
  dialect: 'mysql'
})

const User = sequelize.define('User', {
  // Model attributes
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

// Sync the model with the database
async function syncModel() {
  await User.sync()
  console.log('User model was synchronized successfully.')
}

syncModel()
```

## Adding Associations

Associations define relationships between models. Sequelize supports various types of associations, including `hasOne`, `belongsTo`, `hasMany`, and `belongsToMany`.

### Example: Defining Associations

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
})

// Define associations
const User = require('./user')
User.hasMany(Post)
Post.belongsTo(User)

// Sync the models with the database
async function syncModels() {
  await sequelize.sync()
  console.log('Models were synchronized successfully.')
}

syncModels()
```

## Adding Validation

Sequelize provides built-in validation for model attributes. You can add validation rules to ensure data integrity.

### Example: Adding Validation

```javascript
const User = sequelize.define('User', {
  name: {
    type: DataTypes.STRING,
    allowNull: false,
    validate: {
      notEmpty: true
    }
  },
  email: {
    type: DataTypes.STRING,
    allowNull: false,
    unique: true,
    validate: {
      isEmail: true
    }
  }
})
```

## Conclusion

In this lesson, we explored how to define models in Sequelize. We covered the basics of defining models, setting up associations, and adding validation. In the next lesson, we will learn how to perform CRUD operations with Sequelize models.

## Exercise

[Exercise: Defining Models with Sequelize](exercise.md)
