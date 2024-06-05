# Setting Up the Project

## Overview

In this lesson, we will set up the project structure, configure the Express server, initialize Sequelize, define models, and set up basic routes. This setup will lay the foundation for building a RESTful API.

## Project Structure

We will organize our project with the following structure:

```
express-sequelize-demo/
├── models/
│   ├── user.js
│   └── post.js
├── routes/
│   └── index.js
├── app.js
└── package.json
```

## Setting Up the Express Server

1. **Create `app.js`**:
    - This file will contain the setup code for the Express server and Sequelize.

```javascript
// app.js
const express = require('express')
const { Sequelize } = require('sequelize')
const UserModel = require('./models/user')
const PostModel = require('./models/post')

const app = express()
const PORT = process.env.PORT || 3000

app.use(express.json())

// Initialize Sequelize
const sequelize = new Sequelize('test_db', 'root', 'password', {
  host: 'localhost',
  dialect: 'mysql'
})

// Test the connection
sequelize.authenticate()
  .then(() => {
    console.log('Connection has been established successfully.')
  })
  .catch(err => {
    console.error('Unable to connect to the database:', err)
  })

// Define models
const User = UserModel(sequelize)
const Post = PostModel(sequelize)

// Sync models
sequelize.sync()
  .then(() => {
    console.log('Models synchronized successfully.')
  })
  .catch(err => {
    console.error('Error synchronizing models:', err)
  })

// Import routes
const routes = require('./routes')
app.use('/api', routes)

app.get('/', (req, res) => {
  res.send('Welcome to the Express-Sequelize demo!')
})

app.listen(PORT, () => {
  console.log(`Server is running on port ${PORT}`)
})
```

## Defining Models

1. **Create `models/user.js`**:
    - Define the `User` model.

```javascript
// models/user.js
const { DataTypes } = require('sequelize')

module.exports = (sequelize) => {
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
  return User
}
```

2. **Create `models/post.js`**:
    - Define the `Post` model.

```javascript
// models/post.js
const { DataTypes } = require('sequelize')

module.exports = (sequelize) => {
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

  // Associations
  Post.associate = models => {
    Post.belongsTo(models.User)
  }

  return Post
}
```

## Setting Up Routes

1. **Create `routes/index.js`**:
    - Define basic routes for the API.

```javascript
// routes/index.js
const express = require('express')
const router = express.Router()

// Define a simple route for testing
router.get('/', (req, res) => {
  res.send('API is working!')
})

// Export the router
module.exports = router
```

## Testing the Database Connection and Models

1. **Test the connection and model synchronization**:
    - Run the server and check the console for connection and model synchronization status.

```bash
node app.js
```

If the connection and synchronization are successful, you should see messages indicating that the connection has been established and the models have been synchronized successfully.

## Conclusion

In this lesson, we set up the project structure, configured the Express server, initialized Sequelize, defined models, and set up basic routes. We also tested the database connection and model synchronization to ensure everything is set up correctly.
