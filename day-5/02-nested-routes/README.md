# Nested Routes in Express

## Objective
Learn how to implement and organize nested routes in Express using a modular approach to manage complex URL structures effectively.

## Introduction to Nested Routes
Nested routes allow for the management of URLs that have multiple levels, such as `/users/:userId/posts/:postId/comments`, reflecting resource hierarchy. Modularizing these routes into separate files keeps the application organized and scalable.

## Step 1: Set Up Your Express App
Ensure you have a basic Express setup. If not, create a new Express project with the necessary initial configuration.

## Step 2: Create Modular Route Files
Organize routes into separate modules for users, posts, and comments. This structure helps manage each set of route logic independently.

### Users Router
Create a file `usersRouter.js` in a new directory called `routes`.

```javascript
const express = require('express')
const router = express.Router()
const postsRouter = require('./postsRouter')

// Route to get all users
router.get('/', (req, res) => {
    res.send('List of Users')
})

// Route to get a specific user
router.get('/:userId', (req, res) => {
    res.send(`Details of User ${req.params.userId}`)
})

// Nested posts router
router.use('/:userId/posts', postsRouter)

module.exports = router
```

### Posts Router
Create a file `postsRouter.js` in the `routes` directory.

```javascript
const express = require('express')
const router = express.Router({ mergeParams: true })
const commentsRouter = require('./commentsRouter')

// Route to get all posts for a user
router.get('/', (req, res) => {
    res.send(`List of posts for User ${req.params.userId}`)
})

// Route to get a specific post
router.get('/:postId', (req, res) => {
    res.send(`Details of Post ${req.params.postId} for User ${req.params.userId}`)
})

// Nested comments router
router.use('/:postId/comments', commentsRouter)

module.exports = router
```

### Comments Router
Create a file `commentsRouter.js` in the `routes` directory.

```javascript
const express = require('express')
const router = express.Router({ mergeParams: true })

// Route to get all comments for a post
router.get('/', (req, res) => {
    res.send(`List of comments for Post \${req.params.postId}`)
})

// Route to get a specific comment
router.get('/:commentId', (req, res) => {
    res.send(`Details of Comment ${req.params.commentId} for Post ${req.params.postId}`)
})

module.exports = router
```

## Step 3: Integrate Modular Routes in Main Application
In your main application file, integrate the modular routes.

```javascript
const express = require('express')
const app = express()
const usersRouter = require('./routes/usersRouter')

app.use('/users', usersRouter)

const PORT = 3000
app.listen(PORT, () => console.log('Server running on http://localhost:${PORT}'))
```

## Exercise

[Exercise: Add a Router Module to an Express App](exercise.md)