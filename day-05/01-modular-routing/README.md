# Modular Routes in Express

## Objective
Learn how to organize routes into separate modules in an Express application, enhancing code maintainability and scalability.

## Step 1: Set Up Your Express App
Start with a basic Express setup. If you haven't set up an Express application yet, refer back to the initial demos for creating a basic server.

## Step 2: Create Route Modules
Organize routes by creating separate files for different resources. For this demo, we will create a module for user routes.

```javascript
// Create a new file named 'userRoutes.js' in a 'routes' directory

const express = require('express')
const router = express.Router()

// GET users listing
router.get('/', (req, res) => {
    res.send('GET request for listing all users')
})

// POST request to add a new user
router.post('/', (req, res) => {
    res.send('POST request to add a new user')
})

// PUT request to update an existing user
router.put('/:id', (req, res) => {
    res.send(`PUT request to update user \${req.params.id}`)
})

// DELETE request to delete an existing user
router.delete('/:id', (req, res) => {
    res.send(`DELETE request to remove user \${req.params.id}`)
})

module.exports = router
```

## Step 3: Integrate Route Modules in Your Main App
In your main Express application file, import the route module and use it for specific path prefixes.

```javascript
const express = require('express')
const app = express()

// Import the user routes
const userRoutes = require('./routes/userRoutes')

// Use the user routes for the '/users' path
app.use('/users', userRoutes)

const PORT = 3000
app.listen(PORT, () => console.log('Server running on http://localhost:${PORT}'))
```

## Step 4: Test Your Routes
Use a tool like Postman or curl to test each of the user routes to ensure they are being handled correctly.
