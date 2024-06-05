# Exercise: Creating a Basic HTTP Server

## Objective
Develop understanding of HTTP server basics by building a simple HTTP server in Node.js.

## Task
Create a Node.js script that builds an HTTP server which responds to root path requests with a welcome message.

## Instructions
1. Create a new JavaScript file named `simpleServer.js`.
2. Use the `http` module to create an HTTP server.
3. Configure the server to respond to requests to the root path (`/`) with the text "Welcome to my Node.js server!".
4. Ensure the server listens on port 3000 and logs a message to the console when it starts.

## Example Console Output When Starting the Server
    Server is running on http://localhost:3000

## Advanced Challenge
Enhance the server to handle different routes (`/about`, `/contact`) and respond with different messages for each route.

### Steps for Advanced Challenge
1. Implement route handling for `/about` that responds with "About Us".
2. Implement route handling for `/contact` that responds with "Contact Us".
3. Ensure the server provides a 404 Not Found response for any undefined routes.

## Sample Browser Output for Advanced Challenge
- Accessing `http://localhost:3000/about` should display "About Us".
- Accessing `http://localhost:3000/contact` should display "Contact Us".
- Accessing any other path should display "404 Not Found".
