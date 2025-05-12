

# What is a Callback Function?
A callback function is a function that is passed as an argument to another function and executed later.

1. A function can accept another function as a parameter.
2. Callbacks allow one function to call another at a later time.
3. A callback function can execute after another function has finished.

```bash
function greet(name, callback) {
    console.log("Hello, " + name);
    callback();
}

function sayBye() {
    console.log("Goodbye!");
}

greet("Ajay", sayBye);

output:
Hello, Ajay
Goodbye!

```

### How Do Callbacks Work in JavaScript?
JavaScript executes code line by line (synchronously), but sometimes we need to delay execution or wait for a task to complete before running the next function. Callbacks help achieve this by passing a function that is executed later.
```bash
console.log("Start");

setTimeout(function () {
    console.log("Inside setTimeout");
}, 2000);

console.log("End");

output:
Start
End
Inside setTimeout  (after 2 seconds)

```
1. setTimeout() is an asynchronous function that takes a callback to execute after 2 seconds.
2. The rest of the code continues executing without waiting.

## Where Are Callbacks Used?

### 1. Handling Asynchronous Operations

**Callbacks are widely used in**

1. API requests (fetching data)
2. Reading files (Node.js file system)
3. Event listeners (clicks, keyboard inputs)
4. Database queries (retrieving data)


### 2. Callbacks in Functions Handling Operations
When a function needs to execute different behaviors based on input, callbacks make the function flexible.
```bash
function calc(a, b, callback) {
    return callback(a, b);
}

function add(x, y) {
    return x + y;
}

function mul(x, y) {
    return x * y;
}

console.log(calc(5, 3, add));    
console.log(calc(5, 3, mul));

output:
8
15

```
1. calculate() receives two numbers and a function (add or multiply).
2. The passed function is executed inside calculate().


### 4. Callbacks in API Calls (Fetching Data)
Callbacks are useful when retrieving data from APIs.

```bash
function fetch(callback) {
    fetch("https://jsonplaceholder.typicode.com/todos/1")
        .then(response => response.json())
        .then(data => callback(data))
        .catch(error => console.error("Error:", error));
}

function handle(data) {
    console.log("Fetched Data:", data);
}

fetch(handle);
```
**fetchData() gets data from an API and passes it to handleData() for processing.**

### Features of JavaScript Callbacks
1. Asynchronous Execution: Handle async tasks like API calls, timers, and events without blocking execution.
2. Code Reusability: Write modular code by passing different callbacks for different behaviors.
3. Event-Driven Programming: Enable event-based execution (e.g., handling clicks, keypresses).
4. Error Handling: Pass errors to callbacks for better control in async operations.
5. Non-Blocking Execution: Keep the main thread free by running long tasks asynchronously.


## Problems with Callbacks

### 1. Callback Hell (Nested Callbacks)
When callbacks are nested deeply, the code becomes unreadable and hard to maintain.
```bash
function step1(callback) {
    setTimeout(() => {
        console.log("Step 1 completed");
        callback();
    }, 1000);
}

function step2(callback) {
    setTimeout(() => {
        console.log("Step 2 completed");
        callback();
    }, 1000);
}

function step3(callback) {
    setTimeout(() => {
        console.log("Step 3 completed");
        callback();
    }, 1000);
}

step1(() => {
    step2(() => {
        step3(() => {
            console.log("All steps completed");
        });
    });
});

```
As the number of steps increases, the nesting grows deeper, making the code difficult to manage


### 2. Error Handling Issues in Callbacks
Error handling can get messy when dealing with nested callbacks.

```bash
function divide(a, b, callback) {
    if (b === 0) {
        callback(new Error("Cannot divide by zero"), null);
    } else {
        callback(null, a / b);
    }
}

function result(error, result) {
    if (error) {
        console.log("Error:", error.message);
    } else {
        console.log("Result:", result);
    }
}

divide(10, 2, result);
divide(10, 0, result);

output:
Handling errors inside callbacks can complicate code readability.

```