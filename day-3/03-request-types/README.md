# Handling Different HTTP Requests in Node.js

## Introduction

Understanding how to handle different types of HTTP requests is crucial for building web servers. This guide will demonstrate how to manage GET, POST, PUT, and DELETE requests using the `http` module in Node.js.

## Setup

To handle different HTTP methods, you will create a simple server that responds differently depending on the request type.

## Code Example

```javascript
const http = require('http')

const server = http.createServer((req, res) => {
    // Handle HTTP GET
    if (req.method === 'GET') {
        res.writeHead(200, { 'Content-Type': 'text/plain' })
        res.end('Received a GET request\n')
    }

    // Handle HTTP POST
    else if (req.method === 'POST') {
        res.writeHead(200, { 'Content-Type': 'text/plain' })
        res.end('Received a POST request\n')
    }

    // Handle HTTP PUT
    else if (req.method === 'PUT') {
        res.writeHead(200, { 'Content-Type': 'text/plain' })
        res.end('Received a PUT request\n')
    }

    // Handle HTTP DELETE
    else if (req.method === 'DELETE') {
        res.writeHead(200, { 'Content-Type': 'text/plain' });
        res.end('Received a DELETE request\n');
    }

    // Default response for other methods
    else {
        res.writeHead(405)
        res.end(`${req.method} is not allowed on this server`)
    }
})

const PORT = 3000
server.listen(PORT, () => {
    console.log(`Server running on http://localhost:${PORT}`)
});
```

### Running the Server

1. Save the above code to a file named `server.js`.
2. Run the server by typing `node server.js` in your command line.
3. Test different requests using a tool like Postman or curl.

## Testing with curl

Here are some examples of how to test your server using curl:

- **GET Request**
```bash
curl http://localhost:3000
```

- **POST Request**
```bash
curl -X POST http://localhost:3000
```

- **PUT Request**
```bash
curl -X PUT http://localhost:3000
```

- **DELETE Request**
```bash
curl -X DELETE http://localhost:3000
```

## Exercise

[Exercise: Managing HTTP Requests and Responses](exercise.md)
