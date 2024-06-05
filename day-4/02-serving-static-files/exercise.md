# Exercise: Serve a Simple Website with Express

## Objective
Implement your knowledge of serving static files by setting up an Express server that delivers a simple website comprising multiple static files.

## Task
Create an Express application that serves a small static website. The website should include an HTML file, a CSS file, and an image.

## Instructions
1. **Set Up Your Project**:
   - Create a new directory for your project if you haven't already from previous exercises.
   - Initialize a new Node.js project and install Express if not done previously.

2. **Create a Public Directory**:
   - Inside your project, create a directory named `public`. This will hold all your static files.

3. **Add Static Files**:
   - Add the following files to the `public` directory:

    - **index.html**: Create a simple HTML file with links to your CSS file and an image.
    - **style.css**: Add some basic styling to style your HTML content.
    - **image.jpg**: Place any image you like that will be displayed on your HTML page.

4. **Run Your Server**:
   - Start your Express application by running it from your terminal:

   \`\`\`bash
   node app.js
   \`\`\`

5. **Test Your Application**:
   - Open a web browser and navigate to `http://localhost:3000/index.html`.
   - Ensure that your HTML page is displayed correctly with styles and an image.

## Expected Output
- You should see your HTML page styled by your CSS file and displaying your chosen image.

