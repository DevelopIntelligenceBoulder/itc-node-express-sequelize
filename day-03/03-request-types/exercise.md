# Exercise: Managing HTTP Requests and Responses

## Objective
Learn to handle various types of HTTP requests using a Node.js server.

## Task
Create a Node.js script that builds an HTTP server capable of accepting POST requests at a `/login` route and responding with a success or error message based on the presence of username and password in the request body.

## Instructions
1. Create a new JavaScript file named `loginServer.js`.
2. Use the `http` module to create an HTTP server.
3. Configure the server to handle POST requests to the `/login` route. Check if the username and password are provided in the request body.
4. Respond with "Login Successful!" if both username and password are provided, otherwise respond with "Login Failed: Username and password are required."
5. Ensure the server listens on port 3000 and logs a message to the console when it starts.

## Example Console Output When Starting the Server
    Server is running on http://localhost:3000

## Advanced Challenge
Add handling for a PUT request to update user data and a DELETE request to remove a user.

### Steps for Advanced Challenge
1. Create a route handler for PUT requests to `/update`. This should accept a username and any other user attribute to update. Respond with "Update Successful!" if the username exists.
2. Create a route handler for DELETE requests to `/delete`. This should require a username and delete the user if they exist. Respond with "Deletion Successful!" if the user was found and deleted.
3. For both PUT and DELETE, respond with "Operation Failed: User not found." if the username is not provided or does not exist.

## Sample Browser Test
- Send a PUT request to `http://localhost:3000/update` with a username and attribute to update and see "Update Successful!".
- Send a DELETE request to `http://localhost:3000/delete` with a username to see "Deletion Successful!".
- Omit the username or use a non-existent username in either request to see "Operation Failed: User not found."
