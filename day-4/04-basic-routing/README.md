# Basic Routing in Express

## Objective
Learn how to implement basic routing in an Express application to handle various HTTP methods and paths.

## Step 1: Set Up Your Express App
If you haven't set up a basic Express application yet, start by creating one. You can refer back to earlier demos on setting up an Express server.

## Step 2: Define Routes
Implement various routes to demonstrate handling different HTTP methods and paths.

```javascript
const express = require('express')
const app = express()

// Middleware to parse JSON bodies
app.use(express.json())

// GET route
app.get('/users', (req, res) => {
    res.send('GET Request to the homepage')
})

// POST route
app.post('/users', (req, res) => {
    res.send('POST Request to the homepage')
})

// PUT route
app.put('/users/:id', (req, res) => {
    res.send(\`PUT Request to user ${req.params.id}`)
})

// DELETE route
app.delete('/users/:id', (req, res) => {
    res.send(`DELETE Request for user ${req.params.id}`)
})

const PORT = 3000
app.listen(PORT, () => console.log('Server running on http://localhost:${PORT}'))
```

## Step 3: Test Your Routes
Use a tool like Postman or curl to test each of the routes to ensure they are handling requests correctly.
