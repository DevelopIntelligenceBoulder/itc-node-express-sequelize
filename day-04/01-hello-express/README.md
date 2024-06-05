# Hello Express: Creating a Simple Express Application

## Objective
Learn how to install the Express framework and create a basic application that responds with "Hello Express" when accessed.

## Step 1: Install Express
First, ensure that you have Node.js and npm (Node Package Manager) installed on your system. Then, create a new directory for your project and initialize a new Node.js project.

```bash
mkdir hello-express
cd hello-express
npm init -y
```

This command sets up a new package.json file with default values. Now, install Express using npm:

```bash
npm install express
```

## Step 2: Create Your First Express App
Create a new file named `app.js` and open it in your favorite code editor. Add the following code to set up a basic Express server:

```javascript
const express = require('express')
const app = express()

app.get('/', (req, res) => {
    res.send('Hello Express')
})

const PORT = 3000
app.listen(PORT, () => console.log(`Server running on http://localhost:${PORT}`))
```

## Step 3: Run Your Express App
To start your Express application, run the following command in your terminal:

```bash
node app.js
```

## Testing the Application
Open a web browser and go to `http://localhost:3000`. You should see "Hello Express" displayed on the page.


## Exercise

[Exercise: Personalized Greeting with Express](exercise.md)
