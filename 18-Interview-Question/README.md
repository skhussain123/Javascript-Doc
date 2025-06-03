




### What is JavaScript?
Answer: JavaScript is a high-level, interpreted programming language used to make web pages interactive.
Explanation: It runs in the browser and allows manipulation of HTML/CSS, handling events, and more.


### 2. Difference between var, let, and const?

* var is function-scoped, can be redeclared.
* let is block-scoped, cannot be redeclared in the same scope.
* const is also block-scoped, but its value can't be reassigned.
Explanation: Helps manage variable scope and immutability.


### 3. What is a closure?
Answer: A closure is a function that remembers its outer variables even after the outer function has finished executing.
Explanation: Useful for data encapsulation and creating private variables.


### What are data types in JavaScript?
Answer:

Primitive: String, Number, Boolean, Null, Undefined, Symbol, BigInt

Non-Primitive: Object, Array, Function
Explanation: Understanding helps in type-checking and memory management.


### Difference between == and ===?
Answer:

1. == checks value only (type coercion).
2. === checks value and type (strict equality).
3. Explanation: Use === to avoid unexpected type conversions.


### What is hoisting?

Answer: JavaScript's behavior of moving declarations (not initializations) to the top of the scope.
Explanation: Only var declarations and function declarations are hoisted.


### What is the use of typeof?
Answer: Returns the type of a variable (e.g., "number", "string", "object").
Explanation: Useful for debugging and checking variable types.


### What is NaN?
Answer: Stands for "Not-a-Number", result of invalid numeric operations.
Explanation: typeof NaN is "number", which can be confusing.


### What is event bubbling?
Answer: The event propagates from the target element up to its ancestors.
Explanation: Useful in event delegation.


### What is event delegation?
Answer: Using a single event listener on a parent to handle events from its children.
Explanation: Improves performance, especially for dynamic elements


### What is an array in JavaScript?
Answer: A special object for storing ordered collections.
Explanation: Supports indexed access and various methods like push(), pop().


### What is a function?
Answer: A reusable block of code that performs a task.
Explanation: Defined using function keyword or arrow s


### What is the DOM?
Answer: Document Object Model - a programming interface for HTML/XML.
Explanation: Allows JavaScript to interact with page content.


### What is null vs undefined?

null is intentional absence of value.
* undefined means a variable was declared but not assigned.
* Explanation: Often confused, but used differently.

### How to create an object?
```bash
const obj = { name: "John", age: 30 };
```

### What is the difference between function declaration and expression?
Answer:

Declaration: function greet() {} — hoisted.
* Expression: const greet = function() {} — not hoisted.
* Explanation: Scope and hoisting differ.

### What is an arrow function?
```bash
const add = (a, b) => a + b;
```
**Explanation: Short syntax, no this binding.**


### How to check if a variable is an array?
Answer: Array.isArray(value)
Explanation: More reliable than typeof.

### What is a callback function?
Answer: A function passed into another function to be executed later.
Explanation: Used in async operations like AJAX or setTimeout.

### What is setTimeout()?
**Answer: Executes a function after a delay.**
```bash
setTimeout(() => console.log("Hello"), 1000);  
```
**Explanation: Delay is in milliseconds.**

### What is the difference between map() and forEach()?

map() returns a new array.
* forEach() does not return anything (undefined).
* Explanation: Use map() when you want to transform data into a new array.


### What is destructuring in JavaScript?
```bash
const { name, age } = person;
```
**Explanation: Makes code cleaner and more readable.**


### What are template literals?
Answer: Strings that allow embedded expressions using backticks (` ``).
```bash
`Hello, ${name}!`  
```
**Explanation: Useful for string interpolation and multi-line strings.**


### What is the spread operator (...)?
Answer: Expands elements of an iterable or object.

```bash
const newArr = [...arr1, ...arr2];  
```
**Explanation: Useful for cloning or combining arrays/objects.**


### What is the rest parameter?
Answer: Collects all remaining arguments into an array.

```bash
function sum(...args) { return args.reduce((a, b) => a + b); }  
```
**Explanation: Useful for handling an unknown number of arguments.**


### What is the difference between synchronous and asynchronous code?

Synchronous: Blocks execution.
* Asynchronous: Executes later without blocking.
* Explanation: Async code improves performance, especially for I/O.

### What is a Promise?
Answer: An object representing the eventual completion or failure of an async operation.
```bash
new Promise((resolve, reject) => { ... });  
```
**Explanation: Use .then(), .catch(), or async/await.**


### What is async/await?
Answer: Syntactic sugar over Promises to handle async code like synchronous code.

```bash
const data = await fetchData();  
```
**Explanation: Makes code cleaner and easier to read.**


### What is a higher-order function?
Answer: A function that takes other functions as arguments or returns a function.
Explanation: Examples include map, filter, and reduce.

### What is the this keyword?
Answer: Refers to the object from which the function was called.
Explanation: Its value depends on how the function is called (context-sensitive).


### How does bind() work?
Answer: Creates a new function with this bound to the provided object.
```bash
const boundFn = fn.bind(obj);  
```
**Explanation: Used to control the value of this.**


### What is call() and apply()?

* call() invokes a function with a given this and arguments.
* apply() is the same but takes arguments as an array.
Explanation: Allows borrowing methods and setting context.


### What is a prototype?
Answer: Every object in JavaScript has a prototype, which is another object it inherits properties/methods from.
Explanation: Core to JavaScript inheritance.


### Difference between shallow and deep copy?

* Shallow copy copies only one level deep.
* Deep copy recursively copies all nested levels.
Explanation: Object.assign() and spread create shallow copies.


### How do you clone an object?

* Shallow: { ...obj }
8 Deep: JSON.parse(JSON.stringify(obj)) (limited)
Explanation: Use libraries like Lodash for safe deep copies.


### What is the difference between localStorage, sessionStorage, and cookies?

* localStorage: Permanent until manually cleared.
* sessionStorage: Clears when the tab is closed.
* cookies: Sent with every request, limited in size.
8 Explanation: Storage choice affects performance and persistence.


### What is the difference between null and NaN?

* null: Represents intentional absence of value.
* NaN: Result of an invalid number operation.
Explanation: Both are falsy but represent different issues.


### What are arrow function limitations?

* No this, arguments, super, or new.target.
* Cannot be used as constructors.
Explanation: Good for short, non-method functions.


### What is the difference between Object.freeze() and Object.seal()?

* freeze(): Makes object immutable.
* seal(): Prevents adding/removing properties but allows changes.
Explanation: Useful for locking objects from mutation.

### How to handle errors in JavaScript?
Answer: Using try...catch...finally blocks.
```bash
try { ... } catch (e) { ... } finally { ... }  
```



### What is the difference between undefined and not defined?

undefined: Variable declared but not assigned a value.
not defined: Variable is not declared at all.
Explanation: console.log(a) gives undefined if declared, error if not.


### How to convert a string to a number in JavaScript?
Answer: Use Number(), parseInt(), or unary +.
```bash
Number("10"), parseInt("10"), +"10"  
```

### What is the use of isNaN()?
Answer: Checks if a value is NaN.
```bash
isNaN("abc") // true  
```
**Explanation: Good for input validation.**
```bash
let fruits = ["apple", "banana", "mango"];  
```
**Explanation: Arrays are used to store multiple values.**


### How to find the length of an array?
Answer: Using .length property.

```bash
fruits.length;  
```
**Explanation: Counts number of elements.**


### How to loop through an array?

* for loop
* forEach()
* for...of
```bash
fruits.forEach(fruit => console.log(fruit));  
```
**Explanation: Different loops for different situations.**


### What is push() and pop() in arrays?

* push(): Adds item at end.
* pop(): Removes item from end.
Explanation: Mutate the original array.


### What is the difference between slice() and splice()?

* slice(start, end): Returns a new array, does not modify original.
* splice(start, deleteCount): Modifies original array.
Explanation: Use slice() for copying, splice() for changing.


### How do you declare a constant in JavaScript?
```bash
const PI = 3.14;  
```
**Explanation: const creates a block-scoped constant.**


### What is type coercion in JavaScript?
Answer: Automatic conversion of data types.

```bash
"5" + 1 // "51"  
```
**Explanation: JS tries to convert types automatically, which can cause bugs.**


### What is a ternary operator?
Answer: A shortcut for if...else.
```bash
let result = age > 18 ? "Adult" : "Minor";  
```

### What are truthy and falsy values?

* Falsy: false, 0, "", null, undefined, NaN
* Truthy: Anything else
Explanation: Used in conditionals.


### What is the difference between document.getElementById() and querySelector()?

* getElementById() selects by ID only.
* querySelector() can use any CSS selector.
Explanation: querySelector() is more flexible.


### How do you prevent a form from submitting?
```bash
event.preventDefault();  
```
**Explanation: Used in event handlers to stop default behavior.**


### What is the difference between innerHTML and textContent?

* innerHTML: Returns HTML with tags.
* textContent: Returns only text.
Explanation: Use innerHTML when you want to insert HTML.


### What is a function parameter and argument?

* Parameter: Name in function declaration.
* Argument: Actual value passed to function.

```bash
function add(x, y) { return x + y; }  
add(2, 3);  
```
**Explanation: Parameters = placeholders, Arguments = real values.**


### What is recursion in JavaScript?
Answer: A function calling itself.

```bash
function factorial(n) {
  if (n === 0) return 1;
  return n * factorial(n - 1);
}  
```
**Explanation: Used for problems that can be broken into smaller sub-problems.**

### How to write a comment in JavaScript?
```bash
// single line  
/* multi line */  
```
**Explanation: Comments are ignored by the interpreter.**

### What is the use of return statement in a function?
Answer: Returns a value from the function to the caller.
Explanation: Ends function execution and sends value back.

### What are JavaScript operators?
Answer: Symbols used to perform operations.

* Arithmetic: +, -, *, /, %
* Comparison: ==, ===, !=, >, <
* Logical: &&, ||, !
Explanation: Used to manipulate values or logic.


### What is event delegation in JavaScript?
Answer: A technique where a single event listener handles events for multiple child elements by exploiting event bubbling.
Explanation: Improves performance by reducing the number of listeners.


### What are closures?
Answer: A closure is a function that has access to its own scope, the outer function’s scope, and the global scope.

```bash
function outer() {
  let count = 0;
  return function inner() {
    count++;
    return count;
  };
}
```
**Explanation: Allows data encapsulation.**

### What is currying in JavaScript?
Answer: Breaking a function with multiple arguments into a series of functions with one argument each.

```bash
const add = a => b => a + b;  
```
**Explanation: Improves reusability and composition.**


### What is memoization?
Answer: Caching the result of function calls to optimize performance.
Explanation: Useful in expensive computations.

### What is the event loop in JavaScript?
Answer: Mechanism that handles asynchronous callbacks in a single-threaded environment.
Explanation: Enables non-blocking execution using task queues.

### What is the call stack?
Answer: A stack data structure that stores function invocation context.
Explanation: Helps keep track of execution order.


### What is hoisting in JavaScript?
Answer: Variables and function declarations are moved to the top of their scope before code execution.
Explanation: Only declarations are hoisted, not initializations.

### What is the Temporal Dead Zone (TDZ)?
Answer: The time between entering scope and variable declaration where let and const cannot be accessed.
Explanation: Accessing them before declaration throws a ReferenceError.


### What is a generator function?
Answer: A function that can pause and resume its execution using function* and yield.

```bash
function* gen() {
  yield 1;
  yield 2;
}
```
**Explanation: Useful for handling async flows and lazy evaluation.**


### What is the difference between .call(), .apply(), and .bind()?

* call: Calls a function with a given this and args.
* apply: Same but args as array.
* bind: Returns a new function with bound this.
Explanation: Used to control context.


### What is the Symbol data type?
Answer: A unique and immutable primitive used as object keys.
Explanation: Helps avoid name clashes in objects.


### What is Object.create()?
Answer: Creates a new object with a specified prototype.
```bash
const newObj = Object.create(proto);  
```


### What is function throttling?
Answer: Limits how often a function can run.
Explanation: Improves performance on scroll/resize events.

### What is function debouncing?
Answer: Delays execution until a function hasn't been called for a while.
Explanation: Prevents unnecessary function calls.


### What are WeakMap and WeakSet?
Answer: Similar to Map/Set, but keys are weakly referenced, allowing garbage collection.
Explanation: Useful for managing memory.


### What is the difference between setTimeout() and setInterval()?
Answer:

* setTimeout(): Runs once after delay.
* setInterval(): Runs repeatedly after every delay.
Explanation: Used for scheduling code execution.


### What is the difference between == and ===?
Answer:

* ==: Loose equality (with type coercion)
* ===: Strict equality (no type coercion)
Explanation: Use === to avoid bugs.


### What is the new keyword in JavaScript?
Answer: Creates an instance of an object from a constructor function.

```bash
let obj = new MyClass();  
```
**Explanation: Used for creating custom objects.**


### What is the super keyword?
Answer: Refers to the parent class in a subclass.
```bash
class Child extends Parent {
  constructor() {
    super();
  }
}
```
**Explanation: Used in inheritance.**

### What are tagged template literals?
Answer: Custom functions that process template literals.

```bash
tag`Hello ${name}`;  
```
**Explanation: Used for custom formatting, security, or localization.**


### How does JavaScript handle asynchronous code under the hood?
Answer: Using the event loop, call stack, Web APIs, and task queues.
Explanation: JS is single-threaded but handles async using browser APIs.


### What are service workers?
Answer: JS scripts that run in the background, used for offline caching and push notifications.
Explanation: Core of Progressive Web Apps (PWAs).

### What are modules in JavaScript?
Answer: Files that export/import variables/functions.
```bash
export default myFunc;  
import myFunc from './file.js';  
```


### What is dynamic import?
Answer: Loads modules dynamically using import().
```bash
import('./module.js').then(...);  
```
**Explanation: Useful for lazy loading.**


### What is optional chaining (?.) in JavaScript?
Answer: Safe way to access deeply nested properties.
```bash
let name = user?.profile?.name;  
```
**Explanation: Prevents runtime errors.**

### What is nullish coalescing operator (??)?
Answer: Returns right-hand operand only if the left is null or undefined.

```bash
let value = input ?? "default";  
```
**Explanation: Safer than || for fallback values.**

### What is a Proxy in JavaScript?
Answer: An object that wraps another object to customize behavior.

```bash
const proxy = new Proxy(target, handler);  
```
**Explanation: Used for validation, logging, etc.**

### What is Reflect in JavaScript?
Answer: Built-in object to perform default operations on objects.

```bash
Reflect.get(obj, prop);  

```

### How to deep clone an object safely?
Answer: Use libraries like Lodash (_.cloneDeep()) or structuredClone() in modern browsers.
Explanation: Avoids shared references in nested objects.


### What are async generators?
Answer: Combines async functions and generators using async function*.
Explanation: Useful for streaming async data.

### What is the purpose of Object.assign()?
Answer: Copies properties from source to target object.
Explanation: Used for shallow copies.


### What is the difference between enumerable and non-enumerable properties?
Answer: Enumerable properties show up in loops like for...in.
Explanation: Controlled using Object.defineProperty().


### How do Promises differ from async/await?

* Promises use .then() and .catch()
* async/await uses a cleaner syntax
Explanation: async/await is syntactic sugar for Promises.

### What is the global object in JavaScript?

* Browser: window
* Node.js: global
Explanation: It’s the top-level scope.


### How does memory management work in JavaScript?
Answer: Automatic garbage collection using reference counting and mark-and-sweep.
Explanation: Removes unused memory.


### What is a pure function?
Answer: A function that doesn’t change outside state and always returns the same output for same input.
Explanation: Makes code testable and predictable.


### What is a side effect in JavaScript?
Answer: Any operation that modifies state outside its scope (e.g., DOM change, API call).
Explanation: Avoid in pure functions.


### What is composition in JavaScript?
Answer: Combining simple functions to build complex ones.

```bash
const composed = (f, g) => x => f(g(x));  
```
**Explanation: Improves reusability and functional programming.**

### What are Immediately Invoked Function Expressions (IIFE)?
Answer: Functions that execute immediately after defining.

```bash
(function() { ... })();  
```
**Explanation: Used to create private scopes.**


### What is the difference between frontend and backend JavaScript?
Answer:

* Frontend: Runs in browser, handles UI (DOM, events).
* Backend: Runs on server (Node.js), handles data and APIs.
Explanation: JavaScript is full-stack capable.