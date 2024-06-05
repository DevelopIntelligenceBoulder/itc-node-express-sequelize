
# Creating an HTTP Server

## Introduction

This guide will demonstrate the basics of setting up a simple HTTP server in Node.js using the built-in `http` module.

## Setting Up Your Server

To create an HTTP server in Node.js, you'll need to require the `http` module. This module includes methods to create the server and listen on a specific port.

```javascript
const http = require('http')
```

## Creating the HTTP Server

Here's how you can create a simple HTTP server that responds to all requests with a greeting.

```javascript
const server = http.createServer((req, res) => {
  res.statusCode = 200
  res.setHeader('Content-Type', 'text/plain')
  res.end('Hello, World!\n')
})

const PORT = 3000
server.listen(PORT, () => {
  console.log(`Server running at http://localhost:${PORT}/`)
})
```

## Handling Different Requests

To handle different types of requests such as GET and POST, you can check the \`req.method\` property within your server callback. For example, to only respond to GET requests, you might use:

```javascript
if (req.method === 'GET') {
  res.end('Received a GET request')
}
```
## Exercise

[Exercise: Creating a Basic HTTP Server](exercise.md)
