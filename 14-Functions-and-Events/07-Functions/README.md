


# **Functions in JavaScript**
Functions in JavaScript are reusable blocks of code designed to perform specific tasks. They allow you to organize, reuse, and modularize code. It can take inputs, perform actions, and return outputs. 
```bash
function sum(x, y) { 
    return x + y; 
}
console.log(sum(6, 9));

output:
15
```

## **Function Syntax and Working**
A function definition is sometimes also termed a function declaration or function statement. Below are the rules for creating a function in JavaScript:

* Begin with the keyword function followed by,
* A user-defined function name (In the above example, the name is sum)
* A list of parameters enclosed within parentheses and separated by commas (In the above example, parameters are x and y)
* A list of statements composing the body of the function enclosed within curly braces {} (In the above example, the statement is “return x + y”).


### **2: 1. Function Declaration (Named Function)**
Use: When you need a reusable function that can be accessed from anywhere in the code (hoisting is allowed).
```bash
function greet() {
  console.log("Hello!");
}
greet();
```

### **2. Function Expression**
Use: When you want to assign a function to a variable and control its execution.
```bash
const greet = function() {
  console.log("Hello!");
};
greet();
```

### **3. Arrow Function (ES6)**
Use: A shorter syntax for functions that also binds this lexically (doesn’t have its own this).
```bash
const greet = () => {
  console.log("Hello!");
};
greet();
```

### **4. Anonymous Function**
Use: Functions without a name, typically used as arguments (e.g. in callbacks).
```bash
setTimeout(function() {
  console.log("This is anonymous");
}, 1000);
```

```bash
let numbers = [1, 2, 3, 4];

let doubled = numbers.map(function(num) {
  return num * 2;
});

console.log(doubled); // Output: [2, 4, 6, 8]
```

### **5. Immediately Invoked Function Expression (IIFE)**
Use: A function that executes immediately after its definition.
```bash
(function() {
  console.log("IIFE called");
})();
```

### **6. Constructor Function**
Use: Functions used to create objects when used with the new keyword.
```bash
function Person(name) {
  this.name = name;
}
const p1 = new Person("John");
console.log(p1.name);
```

### **7. Generator Function**
Use: Functions that can pause their execution and return multiple values using the yield keyword.
```bash
function* gen() {
  yield 1;
  yield 2;
}
const g = gen();
console.log(g.next().value); // 1
```

### **8. Async Function**
Use: Functions that return a Promise and allow the use of await to handle asynchronous code.
```bash
async function fetchData() {
  let result = await fetch("https://api.com/data");
  console.log(await result.json());
}
```

### **9. Callback Function**
Use: A function passed as an argument to another function, executed at a later time.
```bash
function doSomething(callback) {
  callback();
}
doSomething(() => console.log("Callback executed"));
```

### **10. Higher-Order Function**
Use: Functions that accept another function as an argument or return a function.
```bash
function higher(fn) {
  return function() {
    fn();
  };
}
const wrapped = higher(() => console.log("Hi!"));
wrapped();
```

### **11. Recursive Function**
Use: A function that calls itself to solve a problem.
```bash
function factorial(n) {
  if (n === 1) return 1;
  return n * factorial(n - 1);
}
console.log(factorial(5)); // 120
```

### **12. Method (inside object)**
Use: A function defined inside an object to represent an object’s behavior.
```bash
const user = {
  name: "Ali",
  greet() {
    console.log("Hello, " + this.name);
  }
};
user.greet();
```

### **13. Default Parameters Function**
Use: A function with default values for parameters when the user doesn’t provide them.
```bash
function greet(name = "Guest") {
  console.log("Hello, " + name);
}
greet(); // Hello, Guest
```

### **Nested Functions**
Functions defined within other functions are called nested functions. They have access to the variables of their parent function.
```bash
function outerFun(a) {
    function innerFun(b) {
        return a + b;
    }
    return innerFun;
}

const addTen = outerFun(10);
console.log(addTen(5));

output:
15
```

## **Why Functions?**
* Functions can be used multiple times, reducing redundancy.
* Break down complex problems into manageable pieces.
* Manage complexity by hiding implementation details.
* Can call themselves to solve problems recursively.





