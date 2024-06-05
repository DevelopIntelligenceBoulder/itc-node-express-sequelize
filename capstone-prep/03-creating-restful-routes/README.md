# Creating RESTful Routes

## Overview

In this lesson, we will learn how to create RESTful routes using Express and Sequelize. RESTful routes follow a set of conventions for mapping HTTP requests to CRUD operations. We will define routes for creating, reading, updating, and deleting resources in our application.

## Setting Up Routes

1. **Create the `routes/user.js` file**:
    - Define routes for the `User` model.

```javascript
// routes/user.js
const express = require('express')
const router = express.Router()
const { User } = require('../models')

// GET all users
router.get('/', async (req, res) => {
  try {
    const users = await User.findAll()
    res.json(users)
  } catch (err) {
    res.status(500).json({ error: err.message })
  }
})

// GET a single user by ID
router.get('/:id', async (req, res) => {
  try {
    const user = await User.findByPk(req.params.id)
    if (user) {
      res.json(user)
    } else {
      res.status(404).json({ error: 'User not found' })
    }
  } catch (err) {
    res.status(500).json({ error: err.message })
  }
})

// POST a new user
router.post('/', async (req, res) => {
  try {
    const user = await User.create(req.body)
    res.status(201).json(user)
  } catch (err) {
    res.status(500).json({ error: err.message })
  }
})

// PUT update a user by ID
router.put('/:id', async (req, res) => {
  try {
    const [updated] = await User.update(req.body, {
      where: { id: req.params.id }
    })
    if (updated) {
      const updatedUser = await User.findByPk(req.params.id)
      res.json(updatedUser)
    } else {
      res.status(404).json({ error: 'User not found' })
    }
  } catch (err) {
    res.status(500).json({ error: err.message })
  }
})

// DELETE a user by ID
router.delete('/:id', async (req, res) => {
  try {
    const deleted = await User.destroy({
      where: { id: req.params.id }
    })
    if (deleted) {
      res.status(204).end()
    } else {
      res.status(404).json({ error: 'User not found' })
    }
  } catch (err) {
    res.status(500).json({ error: err.message })
  }
})

module.exports = router
```

2. **Create the `routes/post.js` file**:
    - Define routes for the `Post` model.

```javascript
// routes/post.js
const express = require('express')
const router = express.Router()
const { Post } = require('../models')

// GET all posts
router.get('/', async (req, res) => {
  try {
    const posts = await Post.findAll()
    res.json(posts)
  } catch (err) {
    res.status(500).json({ error: err.message })
  }
})

// GET a single post by ID
router.get('/:id', async (req, res) => {
  try {
    const post = await Post.findByPk(req.params.id)
    if (post) {
      res.json(post)
    } else {
      res.status(404).json({ error: 'Post not found' })
    }
  } catch (err) {
    res.status(500).json({ error: err.message })
  }
})

// POST a new post
router.post('/', async (req, res) => {
  try {
    const post = await Post.create(req.body)
    res.status(201).json(post)
  } catch (err) {
    res.status(500).json({ error: err.message })
  }
})

// PUT update a post by ID
router.put('/:id', async (req, res) => {
  try {
    const [updated] = await Post.update(req.body, {
      where: { id: req.params.id }
    })
    if (updated) {
      const updatedPost = await Post.findByPk(req.params.id)
      res.json(updatedPost)
    } else {
      res.status(404).json({ error: 'Post not found' })
    }
  } catch (err) {
    res.status(500).json({ error: err.message })
  }
})

// DELETE a post by ID
router.delete('/:id', async (req, res) => {
  try {
    const deleted = await Post.destroy({
      where: { id: req.params.id }
    })
    if (deleted) {
      res.status(204).end()
    } else {
      res.status(404).json({ error: 'Post not found' })
    }
  } catch (err) {
    res.status(500).json({ error: err.message })
  }
})

module.exports = router
```

3. **Update `app.js` to use the new routes**:
    - Import and use the new routes.

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
const userRoutes = require('./routes/user')
const postRoutes = require('./routes/post')
app.use('/api/users', userRoutes)
app.use('/api/posts', postRoutes)

app.get('/', (req, res) => {
  res.send('Welcome to the Express-Sequelize demo!')
})

app.listen(PORT, () => {
  console.log(`Server is running on port ${PORT}`)
})
```

## Conclusion

In this lesson, we learned how to create RESTful routes using Express and Sequelize. We defined routes for the `User` and `Post` models, enabling us to perform CRUD operations. 
