# Integrating CORS with Express

## Objective
Learn how to configure Cross-Origin Resource Sharing (CORS) in an Express application to allow or restrict requests from different domains.

## Introduction to CORS
CORS is a mechanism that uses additional HTTP headers to tell browsers to give a web application running at one origin, access to selected resources from a different origin. This is commonly needed in APIs that are intended to be accessed in client-side applications that reside on different domains.

## Step 1: Set Up Your Express App
If your Express app isn't already set up, refer back to the initial demos for creating a basic server.

## Step 2: Install CORS Middleware
Express uses middleware to enable CORS with various options. First, install the CORS package:

```bash
npm install cors
```

## Step 3: Configure CORS in Your Express App
You can configure CORS globally or on a per-route basis. Here’s how to apply it globally:

```javascript
const express = require('express')
const cors = require('cors')
const app = express()

// Enable all CORS requests
app.use(cors())

app.get('/', (req, res) => {
    res.send('CORS enabled for all origins!')
})

const PORT = 3000
app.listen(PORT, () => console.log(`Server running on http://localhost:${PORT}`))
```

### Configuring CORS for Specific Routes
If you want to enable CORS only for specific routes or set specific options:

```javascript
app.get('/data', cors(), (req, res) => {
    res.json({ message: 'This route has CORS enabled for all origins!' })
})

// Custom CORS for a specific domain
const corsOptions = {
    origin: 'http://example.com',
    optionsSuccessStatus: 200 // some legacy browsers (IE11, various SmartTVs) choke on 204
}
app.post('/update', cors(corsOptions), (req, res) => {
    res.json({ message: 'CORS enabled for only example.com' })
})
```

## Step 4: Test CORS Configuration
Use tools like Postman or a web browser to test accessing your API from different origins to ensure CORS headers are set correctly.
