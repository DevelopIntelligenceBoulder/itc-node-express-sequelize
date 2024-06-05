# Reading URL Path Segments in Node.js

## Introduction

This guide demonstrates how to read path segments from a URL using Node.js's built-in `http` and `url` modules. Path segments are the parts of the URL path split by slashes, which are often used to determine the resource hierarchy or action in web applications.

## Setup

Create a simple server that extracts path segments from the URL and logs them to the console.

## Code Example

```javascript
const http = require('http')
const url = require('url')

const server = http.createServer((req, res) => {
    // Parse the URL
    const parsedUrl = url.parse(req.url, true)

    // Extract path segments
    const segments = parsedUrl.pathname.split('/').filter(segment => segment)

    // Log the path segments to the console
    console.log('Path Segments:', segments)

    // Send a response to the client
    res.writeHead(200, { 'Content-Type': 'text/plain' })
    res.end('Check the server console to see the path segments!')
});

const PORT = 3000
server.listen(PORT, () => {
    console.log(`Server running on http://localhost:${PORT}`)
});
```

## Running the Server

1. Save the above code to a file named `segmentServer.js`.
2. Run the server by typing `node segmentServer.js` in your command line.
3. Test different requests using a tool like a web browser or curl.

## Testing with a Web Browser

Open a web browser and navigate to `http://localhost:3000/products/123/details`. This URL includes path segments for `products`, `123`, and `details`.

## Testing with curl

You can also test using curl from the command line:

```bash
curl http://localhost:3000/products/123/details
```

Expected Output
The server console will log the path segments as an array:
```
Path Segments: ['products', '123', 'details']
```
