# Exercise: Personalized Greeting with Express

## Objective
Enhance your basic Express application to respond with personalized greetings based on a path parameter.

## Task
Modify your existing Express server to include a route that captures a name from the URL and then uses this name to greet the user personally.

## Instructions
1. **Modify Your Express Server**:
   - Add a new route that responds to GET requests at `/hello/:name`.
   - This route should extract the name from the URL and respond with a greeting message that includes the name.

2. **Example Code**:
   ```javascript
   app.get('/hello/:name', (req, res) => {
       const name = req.params.name
       res.send(`Hello, ${name}!`)
   })
   ```

3. **Run Your Server**:
   - Ensure your server is still running, or restart it if necessary.

4. **Test Your Application**:
   - Use a web browser or a tool like curl to test your new route.
   - Example: Navigate to `http://localhost:3000/hello/Alice` to see the personalized greeting.

## Expected Output
- When you navigate to `http://localhost:3000/hello/Alice`, the browser should display:
  ```
  Hello, Alice!
  ```
