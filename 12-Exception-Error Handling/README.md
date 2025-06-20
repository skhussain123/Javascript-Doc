

# Javascript Error and Exceptional Handling
In JavaScript, error and exception handling allows you to manage unexpected issues that occur during the execution of your code. By using tools like try, catch, throw, and finally, you can handle errors easily and prevent the program from crashing. This enables you to provide meaningful error messages, debug your code efficiently, and maintain smooth execution.

### What is JavaScript Error?
In JavaScript, an error is a problem that prevents the code from running as expected. Errors can occur during development or while the application is running, causing the program to stop executing properly. There are different types of errors in JavaScript.


### Types of Errors in JavaScript
1. Syntax Errors: This happens when the code doesn’t follow the correct syntax (e.g., missing parentheses, brackets, or commas).
```bash
console.log("Hello World" 
// Missing closing parenthesis

output:
SyntaxError: missing ) after argument list

```

2. Reference Errors: Occurs when we try to access a variable that hasn’t been declared.
```bash
console.log(x); // ReferenceError: x is not defined

output:
ReferenceError: x is not defined

```

3. Type Errors: This happens when a value is not of the expected type (e.g., trying to call a method on undefined).
```bash
let num = 5;
num.toUpperCase(); // TypeError: num.toUpperCase is not a function

output:
TypeError: num.toUpperCase is not a function
```

4. Range Errors: Occurs when a value is out of range, like passing an invalid number to a function.
```bash
let arr = Array(-1); // RangeError: Invalid array length

output:
RangeError: Invalid array length
```

5. Custom Errors: A custom error is an error that you create yourself to give more specific messages that make sense for your app. It helps you explain exactly what went wrong in a way that’s easy to understand and fix.
```bash
throw new Error("Custom error occurred");

output:
Error: Custom error occurred

```

## Exception Handling in JavaScript
Exception handling in JavaScript refers to the process of dealing with errors (exceptions) that occur during the execution of a program. JavaScript provides some mechanisms to catch, handle, and recover from error instead of letting the error stop the program. The most common approach is using try…catch blocks.

1. Try Block: You place code that may potentially throw an error here.
2. Catch Block: This block executes if an error occurs in the try block.
3. finally Block: The Code inside this block will always run, whether an error occurred or not.

```bash
try {
    let res = 10 / 0;
    if (!isFinite(res)) {
        throw new Error("Cannot divide by zero");
    }
    console.log(res);
} catch (error) {
    console.error("Error occurred:", error.message);
} finally {
    console.log("Execution completed");
}

ouput:
Error occurred: Cannot divide by zero
Execution completed


```
In this example

* The try block attempts to divide 10 by 0, which results in Infinity. It then checks if the result is not a finite number using isFinite(). Since division by zero gives Infinity, an error is thrown with the message “Cannot divide by zero.”
* The catch block catches the thrown error and prints “Error occurred: Cannot divide by zero” to the console.
* The finally block always executes, printing “Execution completed” to the console, regardless of whether an error occurred or not.

### Throwing Custom Errors
Sometimes, the standard JavaScript errors are not sufficient for our application needs. In such cases, you can throw custom errors using the throw statement.

```bash
function check(age) {
    if (age < 18) {
        throw new Error("Age must be 18 or above");
    }
    console.log("Access granted");
}
try {
    check(16);
} catch (error) {
    console.error(error.message);
    // Age must be 18 or above
}

output:
Age must be 18 or above
```
In this example

* The check() function checks if the age is less than 18. If it is, it throws an error with the message “Age must be 18 or above.”
* The try block calls the check() function with 16 as the argument. Since 16 is less than 18, an error is thrown.
* The catch block catches the error and displays the error message “Age must be 18 or above” using console.error().

### Using Finally for Cleanup
The final block is executed regardless of whether an error occurred or not.
```bash
try {
    console.log("Trying...");
    throw new Error("An error occurred");
} catch (error) {
    console.error(error.message);
} finally {
    console.log("Cleaning up...");
}
output:
Trying...
An error occurred
Cleaning up...

```

**In this example**

* The try block attempts to execute the code inside it, first printing “Trying…” to the console, then throwing a new error with the message “An error occurred.”
* The catch block catches the thrown error and prints the error message “An error occurred” to the console using console.error().
* The finally block always runs, no matter what, and prints “Cleaning up…” to the console, ensuring any necessary cleanup happens.

### Advanced: try…catch with async/await
```bash
async function fetchData() {
    try {
        let res = await fetch("https://api.example.com/data");
        let d = await res.json();
        console.log(d);
    } catch (error) {
        console.error("Error fetching data:", error.message);
    }
}
fetchData();

output:
Error fetching data: fetch failed

```

### Create Your Own Custom Error Class
```bash
class ValidationError extends Error {
  constructor(message) {
    super(message); // Call parent constructor
    this.name = "ValidationError"; // Custom error name
  }
}

try {
  let username = "";
  if (username === "") {
    throw new ValidationError("Username cannot be empty");
  }
} catch (err) {
  console.log(err.name);    // "ValidationError"
  console.log(err.message); // "Username cannot be empty"
}


```
### Multiple Errors Example
```bash
class InputError extends Error {
  constructor(message) {
    super(message);
    this.name = "InputError";
  }
}

class DatabaseError extends Error {
  constructor(message) {
    super(message);
    this.name = "DatabaseError";
  }
}

try {
  let input = "";
  if (!input) throw new InputError("Missing user input");

  // Simulate DB error
  let dbStatus = false;
  if (!dbStatus) throw new DatabaseError("Database not connected");

} catch (err) {
  if (err instanceof InputError) {
    console.log("Input Issue:", err.message);
  } else if (err instanceof DatabaseError) {
    console.log("DB Issue:", err.message);
  } else {
    console.log("Unknown Error:", err.message);
  }
}

```


**In this example**

1. The fetchData() function uses async to allow asynchronous operations. It tries to fetch data from the URL “https://api.example.com/data” using the fetch() function.
2. If the fetch is successful, it converts the response to JSON format using await res.json() and then logs the data to the console.
3. If an error occurs during the fetch operation (like a network issue), the catch block catches the error and logs an error message with the error details.


### Benefits of Exception Handling
1. Graceful Degradation: If the error occurs, then also the program keeps on running smoothly.
2. Error Logging: It helps by recording error details, making it easier to find and fix problems.
3. Prevents Crashes: It ensures the app doesn’t completely stop working when something goes wrong.


### Best Practices for Error Handling
1. Catch Specific Errors: Handle specific error types if possible.
2. Use finally for Cleanup: Ensure resources are released or closed.
3. Avoid Silent Failures: Always log or handle errors appropriately.
4. Use Custom Errors: Provide meaningful error messages.



# Debugging in JavaScript
Debugging is the process of testing, finding, and reducing bugs (errors) in computer programs. It involves:

1. Identifying errors (syntax, runtime, or logical errors).
2. Using debugging tools to analyze code execution.
3. Implementing fixes and verifying correctness.

### 1. Built-in Debugging Tools
Modern browsers provide built-in JavaScript debuggers, accessible via Developer Tools. Debuggers can be turned on and off, forcing errors to be reported. They allow setting breakpoints and examining variables while code executes.

### Steps to Activate Debugging:

Chrome: Open “More tools” → “Developer tools” → Select “Console”.
Firefox: Open “Web Developer” → “Web Console”.
Edge: Open “Developer Tools” → Select “Console”.
Opera: Open “Developer” → “Developer tools” → “Console”.
Safari: Enable “Show Develop menu in menu bar” under Preferences, then select “Show Error Console”.

### 2. Using console.log()
One of the simplest debugging techniques is logging messages to the console.

```bash
let x = 10;
console.log("Value of x:", x);
```

### 3. Setting Breakpoints
Breakpoints stop execution at specific lines, allowing variable inspection.

Open DevTools (F12 or Ctrl+Shift+I).
Navigate to the “Sources” tab.
Click on line numbers to set breakpoints.
Resume execution using the play button after analysis.

### 4. Using the debugger Keyword
The debugger statement stops execution and opens debugging tools.

```bash
function test() {
    let n = 42;
    debugger; // Execution pauses here
    console.log(n);
}
test();

```
