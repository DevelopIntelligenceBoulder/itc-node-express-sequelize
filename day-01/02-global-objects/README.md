# Understanding Global Objects in Node.js

## Introduction

This guide explores the global objects available in Node.js. These objects are available in all modules without needing to import them, providing essential functionalities that are accessible throughout your application.

## `global`

The `global` object represents the global namespace in Node.js. It is similar to the `window` object in browsers.

### Example:
```javascript
global.myVariable = 123
console.log(myVariable)  // Outputs: 123
```

## `process`

The `process` object provides information about, and control over, the current Node.js process. It includes methods for interacting with the operating system and the running process.

### Example:
```javascript
console.log(process.version)  // Outputs the version of Node.js running
```

## `Buffer`

`Buffer` is used to handle binary data. It can be used to read from files or receive packets over the network.

### Example:
```javascript
const buffer = Buffer.from('Hello, World!')
console.log(buffer.toString())  // Outputs: 'Hello, World!'
```

## `__dirname`

The `__dirname` variable contains the directory name of the current module. This is useful for handling file paths.

### Example:
```javascript
console.log(__dirname)  // Outputs the path of the current directory
```

## `__filename`

The `__filename` variable contains the filename of the current module.

### Example:
```javascript
console.log(__filename)  // Outputs the path of the current file
```

## `console`

The `console` object provides a simple debugging console similar to JavaScript's console mechanism provided by web browsers.

### Example:
```javascript
console.log('Debugging information')
```

## `module`

The `module` object represents the current module, and `exports` is an object that will be exposed as a module. So, anything you assign to `exports` can be accessed by requiring that module.

### Example:
```javascript
exports.myFunction = function() { console.log('Hello, Module!') }
```

## Exercise

[Exercise: Exploring Global Objects](exercise.md)
