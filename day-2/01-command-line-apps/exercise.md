# Exercise: Command Line Calculator

## Objective
Create a simple command line calculator application in Node.js that can perform basic arithmetic operations based on user input.

## Task
Develop a Node.js script named `calculator.js` that reads command line arguments for operations and numbers, performs the requested arithmetic operation, and prints the result to the console.

## Instructions
1. **Create Your Script**:
   - Create a new JavaScript file named `calculator.js`.
   
2. **Handle Command Line Arguments**:
   - Use `process.argv` to read the operation and numbers from the command line.
   - The program should expect input in the form of: `node calculator.js add 5 3`
   - Supported operations should include `add`, `subtract`, `multiply`, and `divide`.

3. **Implement Arithmetic Operations**:
   - Create functions for addition, subtraction, multiplication, and division.
   - Each function should take two numbers as arguments and return the result.

4. **Process Input and Perform Calculations**:
   - Based on the operation provided via command line, call the appropriate function.
   - Ensure your program can handle integer and floating point numbers.
   - Include error handling for invalid inputs (e.g., non-numeric input, division by zero).

5. **Output the Result**:
   - Print the result of the arithmetic operation to the console.

## Example Usage and Output
- **Command**: `node calculator.js add 5 3`
- **Output**: `8`
- **Command**: `node calculator.js divide 10 2`
- **Output**: `5`
- **Command**: `node calculator.js divide 10 0`
- **Output**: `Cannot divide by zero`
