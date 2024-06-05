# Understanding the File System (fs) Module in Node.js

## Introduction

The `fs` module in Node.js provides a suite of functionalities to interact with the file system. It allows you to perform file operations like reading, writing, updating, and deleting files. This guide will demonstrate how to use the `fs` module to handle files in Node.js.

## Getting Started with fs

To use the `fs` module, you need to require it in your Node.js script:

```javascript
const fs = require('fs')
```

## Basic File Operations

### Reading Files

- **Asynchronous read**:

  ```javascript
  fs.readFile('example.txt', 'utf8', (err, data) => {
    if (err) {
      console.error(err)
      return
    }
    console.log(data)
  })
  ```

- **Synchronous read**:
  ```javascript
  try {
    const data = fs.readFileSync('example.txt', 'utf8')
    console.log(data)
  } catch (err) {
    console.error(err)
  }
  ```

### Writing Files

- **Asynchronous write**:

  ```javascript
  fs.writeFile('example.txt', 'Hello World!', (err) => {
    if (err) {
      console.error(err)
      return
    }
    console.log('File has been written')
  })
  ```

- **Synchronous write**:
  ```javascript
  try {
    fs.writeFileSync('example.txt', 'Hello World!')
    console.log('File has been written')
  } catch (err) {
    console.error(err)
  }
  ```

### Deleting Files

- **Asynchronous delete**:
  ```javascript
  fs.unlink('example.txt', (err) => {
    if (err) {
      console.error(err)
      return
    }
    console.log('File deleted')
  })
  ```

### Checking File Existence

- **Asynchronous check**:
  ```javascript
  fs.access('example.txt', fs.constants.F_OK, (err) => {
    console.log(`${err ? 'does not exist' : 'exists'}`)
  })
  ```

## Synchronous vs. Asynchronous Methods

The `fs` module provides both synchronous and asynchronous methods. Asynchronous methods are non-blocking and recommended for handling I/O operations in real applications to avoid blocking the Node.js event loop. However, synchronous methods might be useful in scripting tasks or for initial configuration setups where simplicity and script execution order are more critical.

## Conclusion

The `fs` module is a powerful tool for file handling in Node.js, enabling developers to perform essential file operations efficiently and effectively. Whether you choose synchronous or asynchronous methods depends on your application's needs and performance considerations.

### Appending to Files

- **Asynchronous append**:

  ```javascript
  fs.appendFile('example.txt', ' Data to append', (err) => {
    if (err) throw err
    console.log('The "Data to append" was appended to file!')
  })
  ```

- **Synchronous append**:
  ```javascript
  try {
    fs.appendFileSync('example.txt', ' Data to append')
    console.log('The "Data to append" was appended to file!')
  } catch (err) {
    console.error(err)
  }
  ```

## Exercise

[Exercise: File System Operations](exercise.md)
