# Performing CRUD Operations with Sequelize

## Overview

In this lesson, we will learn how to perform CRUD (Create, Read, Update, Delete) operations using Sequelize. We will explore the methods provided by Sequelize to interact with the database and manage data.

## Creating Records

To create records in the database, use the `create` method. This method creates a new instance of the model and saves it to the database.

### Example: Creating a User

```javascript
// create-user.js
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

async function createUser() {
  await sequelize.sync()

  const user = await User.create({ name: 'Jane Doe', email: 'jane.doe@example.com' })
  console.log('User created:', user.toJSON())

  await sequelize.close()
}

createUser()
```

## Reading Records

To read records from the database, use the `findAll`, `findOne`, or `findByPk` methods.

### Example: Reading Users

```javascript
// read-users.js
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

async function readUsers() {
  await sequelize.sync()

  const users = await User.findAll()
  console.log('All users:', JSON.stringify(users, null, 2))

  await sequelize.close()
}

readUsers()
```

## Updating Records

To update records in the database, use the `update` method.

### Example: Updating a User

```javascript
// update-user.js
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

async function updateUser() {
  await sequelize.sync()

  const user = await User.findOne({ where: { email: 'jane.doe@example.com' } })
  if (user) {
    user.name = 'Jane Smith'
    await user.save()
    console.log('User updated:', user.toJSON())
  }

  await sequelize.close()
}

updateUser()
```

## Deleting Records

To delete records from the database, use the `destroy` method.

### Example: Deleting a User

```javascript
// delete-user.js
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

async function deleteUser() {
  await sequelize.sync()

  const user = await User.findOne({ where: { email: 'jane.doe@example.com' } })
  if (user) {
    await user.destroy()
    console.log('User deleted')
  }

  await sequelize.close()
}

deleteUser()
```

## Conclusion

In this lesson, we explored how to perform CRUD operations using Sequelize. We covered creating, reading, updating, and deleting records. In the next lesson, we will learn about advanced querying with Sequelize.

## Exercise

[Exercise: Performing CRUD Operations with Sequelize](exercise.md)
