# Serving Static Files with Express

## Objective
Learn how to configure an Express application to serve static files such as images, CSS, and JavaScript files, which are essential for building full-fledged web applications.

## Step 1: Set Up Your Express App
Ensure you have a basic Express application setup from the previous demo. If not, refer back to the "Hello Express" demo to create a basic server.

## Step 2: Create a Public Directory
Create a directory named `public` in your project root. This directory will hold all your static files.

```bash
mkdir public
```

## Step 3: Add Static Content
Add some static files to the `public` directory. For example, you can add an HTML file, a CSS file, and an image.

- **index.html**
  ```html
  <!DOCTYPE html>
  <html lang="en">
  <head>
      <meta charset="UTF-8">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <title>Welcome</title>
      <link rel="stylesheet" href="style.css">
  </head>
  <body>
      <h1>Hello, welcome to my site!</h1>
      <img src="image.jpg" alt="Sample Image">
  </body>
  </html>
  ```

- **style.css**
  ```css
  body {
      font-family: Arial, sans-serif;
      margin: 40px;
      text-align: center;
  }
  ```

- Add an image `image.jpg` to the `public` directory.

## Step 4: Serve Static Files
Modify your `app.js` to include middleware to serve static files. Use the `express.static` middleware to serve files from the `public` directory.

```javascript
const express = require('express')
const app = express()

// Serve static files from the 'public' directory
app.use(express.static('public'))

const PORT = 3000
app.listen(PORT, () => console.log('Server running on http://localhost:${PORT}'))
```

## Step 5: Run Your Express App
Start your Express application:

```bash
node app.js
```

## Testing the Application
Open a web browser and navigate to `http://localhost:3000/index.html`. You should see the HTML page you created, styled by the CSS, and displaying the image.

## Exercise

[Exercise: Serve a Simple Website with Express](exercise.md)
