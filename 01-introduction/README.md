

# Introduction to JavaScript
JavaScript is a high-level, interpreted programming language used to make web pages interactive and dynamic.


### Where is JavaScript used?

* Web Development (frontend and backend)
* Mobile Apps (e.g. React Native)
* Desktop Apps (e.g. Electron)
* Game Development
* Server-Side Development (Node.js)
* AI & IoT Projects

### Why JavaScript is known as a lightweight programming language ?
JavaScript is considered a lightweight language due to its low CPU usage, minimalist syntax, and ease of implementation. With no explicit data types and a syntax similar to C++ and Java, it’s easy to learn and runs efficiently in browsers. Unlike heavier languages like Dart or Java, JavaScript, especially with Node.js, performs faster and uses fewer resources. While it has fewer built-in libraries, this makes it more flexible, though external libraries are often needed for advanced functionality. JavaScript’s efficiency and simplicity make it a top choice for web development.


```bash
<html>
<head></head>
<body>
    <h1>Check the console for the message!</h1>
    <script>
        // This is our first JavaScript program
        console.log("Hello, World!");
    </script>
</body>
</html>
```


### Why JavaScript is known as a lightweight programming language ?
JavaScript is considered a lightweight language due to its low CPU usage, minimalist syntax, and ease of implementation. With no explicit data types and a syntax similar to C++ and Java, it’s easy to learn and runs efficiently in browsers. Unlike heavier languages like Dart or Java, JavaScript, especially with Node.js, performs faster and uses fewer resources. While it has fewer built-in libraries, this makes it more flexible, though external libraries are often needed for advanced functionality. JavaScript’s efficiency and simplicity make it a top choice for web development.

Is JavaScript Compiled or Interpreted or both ?
JavaScript is both compiled and interpreted. The V8 engine improves performance by first interpreting code and then compiling frequently used functions for speed. This makes JavaScript efficient for modern web apps. It’s mainly used for web development but also works in other environments. You can learn it through tutorials and examples.

Just-In-Time (JIT) compilation is a technique used by JavaScript engines (like V8) to improve performance. Here’s how it works

Interpretation: Initially, the code is interpreted line-by-line by the engine.
Hot Code Detection: The engine identifies frequently executed code, such as often-called functions.
Compilation: The “hot” code is compiled into optimized machine code for faster execution.
Execution: The compiled machine code is then executed directly, improving performance compared to repeated interpretation.
JIT compilation balances between interpretation (for quick startup) and compilation (for faster execution).


## JavaScript Versions

Let's take a look at the different versions of ECMAScript, their release years, and the key features they introduced.

| Version | Name             | Release Year | Features |
|---------|------------------|--------------|----------|
| ES1     | ECMAScript 1     | 1997         | Initial Release |
| ES2     | ECMAScript 2     | 1998         | Minor Editorial Changes |
| ES3     | ECMAScript 3     | 1999         | Added:<br>- Regular Expressions<br>- try/catch<br>- Exception Handling<br>- switch case and do-while |
| ES4     | ECMAScript 4     | —            | Abandoned due to conflicts |
| ES5     | ECMAScript 5     | 2009         | Added:<br>- JavaScript "strict mode"<br>- JSON support<br>- JS getters and setters |
| ES6     | ECMAScript 2015  | 2015         | Added:<br>- let and const<br>- Class declaration<br>- import and export<br>- for..of loop<br>- Arrow functions |
| ES7     | ECMAScript 2016  | 2016         | Added:<br>- Block scope for variables<br>- async/await<br>- Array.includes function<br>- Exponentiation Operator |
| ES8     | ECMAScript 2017  | 2017         | Added:<br>- Object.values<br>- Object.entries<br>- Object.getOwnPropertyDescriptors |
| ES9     | ECMAScript 2018  | 2018         | Added:<br>- Spread operator<br>- Rest parameters |
| ES10    | ECMAScript 2019  | 2019         | Added:<br>- Array.flat()<br>- Array.flatMap()<br>- Array.sort is now stable |
| ES11    | ECMAScript 2020  | 2020         | Added:<br>- BigInt primitive type<br>- Nullish coalescing operator |
| ES12    | ECMAScript 2021  | 2021         | Added:<br>- String.replaceAll() Method<br>- Promise.any() Method |
| ES13    | ECMAScript 2022  | 2022         | Added:<br>- Top-level await<br>- New class elements<br>- Static block inside classes |
| ES14    | ECMAScript 2023  | 2023         | Added:<br>- toSorted method<br>- toReversed method<br>- findLast, and findLastIndex methods on Array.prototype and TypedArray.prototype |




## Whats new  in ES6

### ✅ 1. let and const (Block-scoped variables)

```bash
let name = "Ali";     // Can be changed
const age = 25;       // Cannot be changed
```
let and const replaced var for safer variable declaration.


### ✅ 2. Arrow Functions () => {}
Shorter syntax for functions:

```bash
const add = (a, b) => a + b;
```

### ✅ 3. Template Literals (Backticks)
Easier string formatting with ${}:

```bash
let name = "Ali";
console.log(`Hello, ${name}!`);
```

### ✅ 4. Default Parameters
Functions can have default values:

```bash
function greet(name = "Guest") {
  console.log(`Hello, ${name}`);
}

```

### ✅ 5. Destructuring
Easily extract values from arrays or objects:

```bash
// Object
const user = { name: "Ali", age: 25 };
const { name, age } = user;

// Array
const [a, b] = [1, 2];

```

### ✅ 6. Spread ... and Rest ... Operators
Spread (Expands items):

```bash
const arr1 = [1, 2];
const arr2 = [...arr1, 3, 4];  // [1, 2, 3, 4]

```

Rest (Collects items):
```bash
function sum(...nums) {
  return nums.reduce((a, b) => a + b);
}
```

### ✅ 7. Classes
Object-oriented programming with cleaner syntax:

```bash
class Person {
  constructor(name) {
    this.name = name;
  }

  greet() {
    return `Hello, ${this.name}`;
  }
}

```

### ✅ 8. Promises
Handle async code better than callbacks:

```bash
let promise = new Promise((resolve, reject) => {
  resolve("Success");
});

promise.then(result => console.log(result));

```

### ✅ 9. Modules (import / export)
Split code into multiple files:

```bash
// greet.js
export function greet() {
  return "Hello";
}

// main.js
import { greet } from './greet.js';
console.log(greet());

```

### ✅ 10. for...of Loop
Iterate over iterable values like arrays:

```bash
const nums = [1, 2, 3];
for (let num of nums) {
  console.log(num);
}

```


### object Literals
An object literal is the simplest way to create objects in JavaScript using key-value pairs.

```bash
const name = "Ahsan";
const age = 22;

const user = {
  name,
  age,
  greet() {
    console.log(`Hi, I'm ${this.name}`);
  }
};

example 2-----

let key = "score";

const game = {
  [key]: 100
};

console.log(game.score);  // 100
```


| Feature            | Description                 |
| ------------------ | --------------------------- |
| `let`, `const`     | Block-scoped variables      |
| Arrow Functions    | Short syntax for functions  |
| Template Literals  | `${}` inside backticks      |
| Default Parameters | Function default values     |
| Destructuring      | Unpack objects/arrays       |
| Spread/Rest `...`  | Merge or collect items      |
| Classes            | Clean OOP syntax            |
| Promises           | Handle async work           |
| Modules            | Import/export between files |
| `for...of`         | Simple loop for arrays      |

