# Exercise: File System Operations

## Objective
Practice reading from and writing to files using the `fs` module in Node.js.

## Task
Create a Node.js script that reads a text file and converts its content to uppercase, then writes the result to a new file.

## Instructions
1. Create a new JavaScript file named `uppercaseConverter.js`.
2. Use the `fs` module to read a text file named `input.txt`.
3. Convert the content of the file to uppercase.
4. Write the converted content to a new file named `output.txt`.
5. Ensure to handle any potential errors during file reading or writing.

## Example Input (input.txt)
    hello world
    this is a test file

## Example Output (output.txt)
    HELLO WORLD
    THIS IS A TEST FILE

## Advanced Challenge
Extend the script to handle JSON files. Parse a JSON file named `data.json`, modify its content by adding a new property to each object, and save it back to the filesystem as `modifiedData.json`.

### Steps for Advanced Challenge
1. Read the JSON file `data.json` containing an array of objects.
2. Add a new property `updatedAt` with the current date and time to each object.
3. Write the modified array back to a new file `modifiedData.json`.

## Sample Input for Advanced Challenge (data.json)
    [
        {"name": "Alice", "age": 25},
        {"name": "Bob", "age": 30}
    ]

## Sample Output for Advanced Challenge (modifiedData.json)
    [
        {"name": "Alice", "age": 25, "updatedAt": "2022-01-01T12:00:00Z"},
        {"name": "Bob", "age": 30, "updatedAt": "2022-01-01T12:00:00Z"}
    ]
