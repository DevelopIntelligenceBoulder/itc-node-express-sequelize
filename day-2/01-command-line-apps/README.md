# Creating Basic Command Line Applications

## Introduction

This guide covers two basic methods to interact with users in a Node.js command-line application: using command-line arguments and interactive input.

## Setting up Your CLI Application

1. **Create a Project Directory**:

   - Open your terminal.
   - Create a new directory for your project and navigate into it:
     ```
     mkdir MyCLIApp
     cd MyCLIApp
     ```

2. **Initialize a Node.js Project**:
   - Run the following command to initialize a new Node.js project:
     ```
     npm init -y
     ```

## Example 1: Using Command-Line Arguments

### Overview

Command-line arguments are passed to Node.js applications via `process.argv`. This array contains the full command-line execution path. The first element is the path to the Node.js executable, the second is the path to the executed script, and the subsequent elements are the additional command-line arguments.

### Create the Script

- Create a file named `app_args.js`.
- Add the following code to handle command-line arguments:

  ```javascript
  // Display the contents of process.argv
  console.log(process.argv)

  // Extract arguments if any
  const args = process.argv.slice(2) // Ignore the first two elements
  console.log('Arguments:', args.join(' '))
  ```

### Run Your Application

- Execute your script with additional arguments:
  ```
  node app_args.js arg1 arg2 arg3
  ```

### Expected Output

- You should see the array of `process.argv` and the arguments listed.

## Example 2: Interactive Input Using process.stdin.on

### Overview

For more interactive applications, `process.stdin.on` allows the program to handle input dynamically, responding to user input events.

### Create the Script

- Create a file named `app_interactive.js`.
- Add the following code to interactively query the user:

  ```javascript
  process.stdout.write('What is your name? ')

  process.stdin.on('data', (data) => {
    const name = data.toString().trim()
    process.stdout.write(`Hello ${name}!
  `)
    process.exit()
  })
  ```

### Run Your Application

- Back in your terminal, run your interactive script:
  ```
  node app_interactive.js
  ```

### Expected Interaction

- You will be prompted to enter your name, and after entering it, the application will greet you by name.

## Conclusion

These examples demonstrate two fundamental ways to gather user input in Node.js command-line applications, both through static command-line arguments and dynamic interactive input. This approach enables building flexible and user-friendly CLI tools.

## Exercise

[Exercise: Command Line Calculator](exercise.md)
