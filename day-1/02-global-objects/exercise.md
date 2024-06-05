# Exercise: Exploring Global Objects

## Objective
Familiarize with Node.js global objects through practical application.

## Task
Write a Node.js script that uses the `process` object to print out:
- The current version of Node.js running on your system.
- The operating system platform.
- The current process ID.

## Instructions
1. Create a new JavaScript file named `processInfo.js`.
2. Use the `process` object to access and print the required information:
   - `process.version` to get the Node.js version.
   - `process.platform` to identify the operating system.
   - `process.pid` to find the process ID.
3. Run your script using Node.js to see the output.

## Example Output
Node.js Version: v14.15.1
Platform: win32
Process ID: 14580

## Advanced Challenge
Modify your script to monitor and log changes in memory usage every 5 seconds. Use `process.memoryUsage()` to get memory usage details.

### Steps for Advanced Challenge
1. Implement a function that logs memory usage details.
2. Use `setInterval` to call this function every 5 seconds.
3. Ensure to format the output for better readability.

## Sample Output for Advanced Challenge
Memory Usage: { rss: 49356800, heapTotal: 18268160, heapUsed: 6504456, external: 49879 }
