# Handling Errors in Express

## Objective
Learn how to effectively manage common HTTP errors in an Express application to improve reliability and user experience.

## Step 1: Set Up Your Express App
Start with a basic Express setup. If you don't already have an Express application from previous demos, refer back to the first demo to set one up.

## Step 2: Create Routes
Add routes to your application, including one that will deliberately cause an error to demonstrate error handling.

```javascript
const express = require('express')
const app = express()

app.get('/', (req, res) => {
    res.send('Welcome to the Express Error Handling Demo!') 
});

// Deliberately cause an error for demonstration
app.get('/error', (req, res) => {
    throw new Error('Something went wrong!')
});

// This route simulates a database operation that could fail
app.get('/data', (req, res, next) => {
    const data = fetchData()
    if (!data) {
        const err = new Error('No data found!')
        err.status = 404  // Custom error status for 404
        next(err);
    } else {
        res.send(data)
    }
})
```

## Step 3: Implement Error Handling Middleware
Add middleware to manage 404 and 500 errors.

```javascript
// Catch 404 errors that were not handled by any routes
app.use((req, res, next) => {
    res.status(404).send('Sorry, that route does not exist.')
});

// General error handling middleware for catching all other errors
app.use((err, req, res, next) => {
    console.error(err.stack)  // Log error for debugging
    res.status(err.status || 500).send(err.message || 'Something broke!')
});
```

## Step 4: Run Your Express App
Start your Express server and access the routes to see different types of error handling in action.

```bash
node app.js
```

## Testing the Application
- Navigate to `http://localhost:3000/` to see the normal operation.
- Navigate to `http://localhost:3000/error` to trigger and view the 500 error handling.
- Navigate to `http://localhost:3000/anythingelse` to test the 404 error handling.
- Navigate to `http://localhost:3000/data` assuming it's set to simulate no data found for 404 error handling.

## Exercise

[Exercise: Enhance Error Handling in Express](exercise.md)
