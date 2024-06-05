# Exercise: Create a RESTful API with Express

## Objective
Practice building a RESTful API using Express by creating an API for managing a specific resource, such as "events".

## Task
Develop an API that allows clients to perform CRUD operations on the "events" resource. Each event should have an `id`, `title`, and `date`.

## Instructions
1. **Setup Your Express Project**:
   - Ensure you have Express installed and set up a basic server if not already done.

2. **Define Event Data**:
   - Use an array to simulate a database that stores events. Initialize it with a few sample events.

3. **Implement CRUD Operations**:
   - Create endpoints for each type of CRUD operation on the events:
     - `GET` to retrieve all events or a single event by ID.
     - `POST` to add a new event.
     - `PUT` to update an existing event.
     - `DELETE` to remove an event.

4. **Testing**:
   - Test each endpoint using a tool like Postman to ensure it behaves as expected.

## Advanced Challenge
Enhance your API with the following features:
   - **Filtering**: Enhance the `GET` endpoint to allow filtering events by `title` and/or `date`. Use query parameters to pass filter options.
   - **Validation**: Add basic validation for `POST` and `PUT` requests to ensure that no essential fields are missing and the date is in a valid format.
   - **Error Handling**: Improve error handling to provide more descriptive messages depending on the type of error (e.g., item not found, validation error).

## Hints
- Remember to set the response status codes appropriately for each operation (e.g., 200 for successful fetch, 201 for created, 404 for not found).
- For pagination, you might add query parameters to your `GET` method to specify page number and size.

## Expected Output
- The API should correctly handle creating, retrieving, updating, and deleting events.
- The advanced features should correctly enhance functionality and robustness of your API.
