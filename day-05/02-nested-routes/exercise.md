# Exercise: Add a Router Module to an Express App

## Objective
Enhance your understanding of Express application structure by adding a new modular router file for managing a specific resource, "products". Implement basic CRUD operations within this new router and explore advanced routing techniques.

## Task
Create a new modular router for handling routes associated with "products". Implement basic CRUD operations and advanced features within this new router.

## Instructions
1. **Create the 'Products' Router File**:
   - Create a new file named `productRoutes.js` in the `routes` directory of your Express project.
   - Define routes for CRUD operations: retrieving all products, adding a new product, updating an existing product, and deleting a product.

2. **Implement CRUD Operations**:
   - Use appropriate HTTP methods for each operation (GET for retrieval, POST for creation, PUT for updating, DELETE for deletion).
   - Each route should send a response that describes the action it performs, such as "Adding a new product".

3. **Integrate the New Router into Your Main App**:
   - Import your new `productRoutes` into the main application file.
   - Mount the router on the `/products` endpoint so that all product-related routes are prefixed with `/products`.

4. **Test Your Routes**:
   - Use tools like Postman or curl to send requests to your routes and verify that they respond as expected.

## Advanced Challenge
   - **Nested Routes**: Implement nested routes under `/products/:productId/reviews` to handle product reviews. Define routes to get all reviews, add a review, and delete a review.
   - **Query Capabilities**: Enhance the `GET /products` route to support filtering by price range and sorting by name or price. This will allow users to query products more effectively.

## Hints
- Remember to export your router using `module.exports` at the end of your `productRoutes.js` file.
- Use `app.use()` in your main application file to incorporate the router at the correct path.
- For the advanced query capabilities, consider how query parameters can be accessed via `req.query` in your route handlers.

## Expected Output
- Your application should be able to handle different types of requests (GET, POST, PUT, DELETE) at routes under `/products`, and each request should return a message indicative of the action taken.
- The advanced section should allow for detailed interactions with products and their reviews, as well as dynamic querying of products based on user-supplied criteria.

## Conclusion
This exercise provides an opportunity to develop a deeper understanding of building and structuring APIs using Express, with a focus on modular routing and advanced API features like nested routes and query capabilities.
