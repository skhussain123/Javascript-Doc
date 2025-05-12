

# Async and Await in JavaScript
Async and Await in JavaScript is used to simplify handling asynchronous operations using promises. By enabling asynchronous code to appear synchronous, they enhance code readability and make it easier to manage complex asynchronous flows.

```bash
async function fetchData() {
  const response = await fetch("https://jsonplaceholder.typicode.com/posts/1");
  const data = await response.json();
  console.log(data);
}

fetchData();

output:
{
  userId: 1,
  id: 1,
  title: ....',
  body: ....}

```

```bash
async function functionName() {
  try {
    const result = await someAsyncFunction();
    console.log(result);
  } catch (error) {
    console.error("Error:", error.message);
  }
}

```

### Async Function
The async function allows us to write promise-based code as if it were synchronous. This ensures that the execution thread is not blocked. Async functions always return a promise. If a value is returned that is not a promise, JavaScript automatically wraps it in a resolved promise.
```bash
async function myFunction() {
  return "Hello";
}

```

```bash
const getData = async () => {
    let data = "Hello World";
    return data;
}

getData().then(data => console.log(data));

output:
Hello World

```

### Await Keyword
The await keyword is used to wait for a promise to resolve. It can only be used within an async block. Await makes the code wait until the promise returns a result, allowing for cleaner and more manageable asynchronous code.

```bash
const getData = async () => {
    let y = await "Hello World";
    console.log(y);
}

console.log(1);
getData();
console.log(2);

output:
1
2
Hello World

```
* The async keyword transforms a regular JavaScript function into an asynchronous function, causing it to return a Promise.
* The await keyword is used inside an async function to pause its execution and wait for a Promise to resolve before continuing.


### Error Handling in Async/Await
JavaScript provides predefined arguments for handling promises: resolve and reject.

1. resolve: Used when an asynchronous task is completed successfully.
2. reject: Used when an asynchronous task fails, providing the reason for failure.

```bash
async function fetchData() {
  try {
    let response = await fetch('https://api.example.com/data');
    let data = await response.json();
    console.log(data);
  } catch (error) {
    console.error('Error fetching data:', error);
  }
}

```

### Advantages of Async and Await
1. Improved Readability: Async and Await allow asynchronous code to be written in a synchronous style, making it easier to read and understand.
2. Error Handling: Using try/catch blocks with async/await simplifies error handling.
3. Avoids Callback Hell: Async and Await prevent nested callbacks and complex promise chains, making the code more linear and readable.
3. Better Debugging: Debugging async/await code is more intuitive since it behaves similarly to synchronous code.
