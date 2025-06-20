


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

**Method 2**
```bash
(async() {
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





# JavaScript Function Binding
JavaScript Function Binding ka matlab hai this keyword ko fix karna, taa keh function jab bhi chale, wo sahi object ke sath hi kaam kare.

## Ye this kya hota hai?
this ka matlab hota hai:

**"Ye function kis object ka hissa hai?"**

Agar this galat object ko point kare, to function ghalat kaam karega ya error dega. Binding se hum this ko lock kar dete hain.

## Q Use Hota Hai?
Kabhi kabhi function apni jagah change kar leta hai (like event ya setTimeout mein), to this kho jata hai. Binding use karte hain taa keh:

* Function ko sahi object ke sath joda ja sake.
* this ki value confuse na ho.
* Callback ya event handlers mein problem na aaye.

## 1: bind() Example

```bash
const user = {
  name: "Ali",
  greet: function() {
    console.log("Hello " + this.name);
  }
};

const greetFunc = user.greet;
greetFunc(); // ❌ this.name is undefined


const greetFuncBound = user.greet.bind(user);
greetFuncBound(); // ✅ Hello Ali


```

## 2: call() Example
```bash
function introduce(city, country) {
  console.log("My name is " + this.name + " and I live in " + city + ", " + country);
}

const person = { name: "Ali" };

introduce.call(person, "Lahore", "Pakistan");
// Output: My name is Ali and I live in Lahore, Pakistan

```
* Yahan call() ne introduce function ko foran chalaya aur this ko person banaya.
* Arguments directly diye: "Lahore", "Pakistan"

## 3: apply() Example
```bash
function introduce(city, country) {
  console.log("My name is " + this.name + " and I live in " + city + ", " + country);
}

const person = { name: "Ali" };

introduce.apply(person, ["Karachi", "Pakistan"]);
// Output: My name is Ali and I live in Karachi, Pakistan
```
apply() bhi same kaam karta hai, lekin arguments array mein pass hote hain: ["Karachi", "Pakistan"]




# JavaScript Iterator
Iterator JavaScript ka ek tareeqa hai step-by-step kisi collection (array, string, etc.) ko read karne ka.

Iterator ek object hota hai jo .next() method provide karta hai, jo next value deta hai — jab tak items khatam na ho jayein.


```bash
const array = [10, 20, 30];
const iterator = array[Symbol.iterator]();

console.log(iterator.next()); // { value: 10, done: false }
console.log(iterator.next()); // { value: 20, done: false }
console.log(iterator.next()); // { value: 30, done: false }
console.log(iterator.next()); // { value: undefined, done: true }

```

### Important Properties of an Iterator:
* .next() → ek object return karta hai:
  * value: current item
  * done: false jab tak aur values bachi hoon, true jab end ho jaye


## Real-Life Use: for...of loop (uses iterator under the hood)
```bash
const colors = ['red', 'blue', 'green'];

for (let color of colors) {
  console.log(color);
}

```
Ye for...of loop internally iterator hi use karta hai.


## Custom Iterator
```bash
function customIterator(items) {
  let index = 0;
  return {
    next: function() {
      return index < items.length
        ? { value: items[index++], done: false }
        : { value: undefined, done: true };
    }
  };
}

const iter = customIterator(['a', 'b', 'c']);
console.log(iter.next()); // { value: 'a', done: false }

```
* Iterator allows step-by-step access to elements.
* Used in loops (for...of) and when dealing with custom data streams.
* Useful for efficient memory handling (e.g., large datasets or generators).




# What is closure?
A closure is a function that allows access to variables from its outer function and global variables, even after the outer function has finished executing. This enables functions to “remember” their environment. Some of the features of the closures are mentioned below:

* A closure allows a function to access variables from its outer (enclosing) function even after it has finished executing.
* Global variables can be made private within a function using closures, ensuring they cannot be accessed or modified directly from outside.
* Closures provide a way to encapsulate private data and create public methods to interact with it.
* Closures help retain references to variables that would otherwise be lost after the execution of the outer function.

```bash
function outer() {
    let outerVar = "I'm in the outer scope!";
    function inner() {
        console.log(outerVar);
    }
    return inner;
}
const closure = outer(); 
closure(); 


```

## Lexical Scoping
Closures are based on lexical scoping, meaning that a function’s scope is determined by where the function is defined, not where it is executed. This allows inner functions to access variables from their outer function.

```bash
function outer() {
    const outerVar = 'I am from outer';

    function inner() {
        console.log(outerVar);
  }

    return inner;
}

const newClosure = outer();
newClosure();

```

## Private Variables
Closures allow a function to keep variables hidden and only accessible within that function. This is often used when creating modules to protect certain data from being accessed or modified by other parts of the program.
```bash
function counter() {
// Private variable
    let count = 0; 
    
    return function () {
     // Access and modify the private variable
        count++;
        return count;
    };
}

const increment = counter();
console.log(increment());
console.log(increment());
console.log(increment());

output:
1
2
3

```

# JavaScript Higher Order Functions

A higher-order function is a function that does one of the following:

* Takes another function as an argument.
* Returns another function as its result.
Higher-order functions help make your code more reusable and modular by allowing you to work with functions like any other value.
```bash
function fun() {
    console.log("Hello, World!");
}
function fun2(action) {
    action();
    action();
}

fun2(fun);


```
* fun2 is a higher-order function because it takes another function (action) as an argument.
* It calls the action function twice.

## 1. Popular Higher Order Functions in JavaScript
The map function is used to transform an array by applying a callback function to each element. It returns a new array.

```bash
const n = [1, 2, 3, 4, 5];
const square = n.map((num) => num * num);
console.log(square);
```

map applies the callback (num) => num * num to each element of numbers.
A new array is returned where each element is the square of the original

## 2. filter
The filter function is used to create a new array containing elements that satisfy a given condition.
```bash
const n = [1, 2, 3, 4, 5];
const even = n.filter((num) => num % 2 === 0);
console.log(even);
```
The callback (num) => num % 2 === 0 filters out elements not divisible by 2.
The resulting array contains only even numbers.


## 3. reduce
The reduce function accumulates array elements into a single value based on a callback function.
```bash
const n = [1, 2, 3, 4, 5];
const sum = n.reduce((acc, curr) => acc + curr, 0);
console.log(sum);
```
The callback (acc, curr) => acc + curr adds all elements.
0 is the initial value of the acc.


## 4. forEach
The forEach function executes a provided function once for each array element.
```bash
const n = [1, 2, 3];
n.forEach((num) => console.log(num * 2));
```
forEach performs the side effect of printing each element multiplied by 2.
It does not return a new array like map.

## 5. find
The find function returns the first element in the array that satisfies a given condition
```bash
const n = [1, 2, 3, 4, 5];
const fEven = n.find((num) => num % 2 === 0);
console.log(fEven);

```
The callback (num) => num % 2 === 0 finds the first even number.
If no element satisfies the condition, it returns undefined.

## 6. some
The some function checks if at least one array element satisfies a condition.
```bash
const n = [1, 2, 3, 4, 5];
const hasNeg = n.some((num) => num < 0);
console.log(hasNeg);
```
The callback (num) => num < 0 checks for negative numbers.
It returns true if any element passes the condition, false otherwise.


## 7. every
The every function checks if all array elements satisfy a condition.
```bash
const n = [1, 2, 3, 4, 5];
const allPos = n.every((num) => num > 0);
console.log(allPos)

```
* The callback (num) => num > 0 checks if all numbers are positive.
* It returns true only if all elements pass the condition.



# JavaScript Function Generator
Generator Function JavaScript mein ek special function hota hai jo pause aur resume ho sakta hai execution ke dauran.

Ye normal function se alag hota hai:

* Normal function poora ek baar chalta hai
* mGenerator function ruk ruk ke chalta hai using yield

```bash
function* generatorFunction() {
  yield 'First';
  yield 'Second';
  yield 'Third';
}



```
* function* ← star lagta hai to mark it as a generator.
* yield ← returns value aur wahan ruk jaata hai.
* Generator function call karne pe ek iterator object milta hai.


```bash
function* greetGenerator() {
  yield "Hello";
  yield "How are you?";
  yield "Goodbye";
}

const greeter = greetGenerator();

console.log(greeter.next()); // { value: 'Hello', done: false }
console.log(greeter.next()); // { value: 'How are you?', done: false }
console.log(greeter.next()); // { value: 'Goodbye', done: false }
console.log(greeter.next()); // { value: undefined, done: true }

```

### Infinite Number Generator
```bash
function* countForever() {
  let i = 1;
  while (true) {
    yield i++;
  }
}

const counter = countForever();
console.log(counter.next().value); // 1
console.log(counter.next().value); // 2
console.log(counter.next().value); // 3 ...


```

###  Generator vs Normal Function
| Feature           | Normal Function | Generator Function          |
| ----------------- | --------------- | --------------------------- |
| Runs all at once? | ✅ Yes           | ❌ No, stops at each `yield` |
| Pause and resume? | ❌ No            | ✅ Yes                       |
| Returns?          | One value       | Many values (using `yield`) |
| Returns type?     | Any             | Iterator Object             |


## Use Case:
| Use Case             | Why Use Generator?                         |
| -------------------- | ------------------------------------------ |
| Large data streams   | Process data step-by-step, not all at once |
| Asynchronous control | Replace `async/await` or callbacks         |
| Infinite sequences   | Like number generators                     |


* function* → Generator function
* yield → Step-by-step value dena + pause
* .next() → Call to get next value
* Useful for lazy loading, large data, infinite loops, and asynchronous tasks


# JavaScript Hoisting

"JavaScript aapke code ke kuch hisso ko automatically upar le jata hai execution se pehle."

* Variables (using var)
* Function declarations ko JavaScript pehle hi memory mein store kar leta hai function ya scope ke start mein, chahe aap ne neeche likha ho.


### Example 1: Variable Hoisting (using var)
```bash
console.log(x); // undefined
var x = 5;

```
**Yahan JavaScript isay aise samajhti hai:**
```bash
var x;
console.log(x); // undefined
x = 5;

```
Note: let aur const hoist to hote hain, lekin unka access pehle nahi milta (TDZ error deta hai).

### Example 2: Function Hoisting
```bash
greet(); // Hello!
function greet() {
  console.log("Hello!");
}

```
JavaScript is function ko poora upar le jata hai — is liye aap use pehle bhi call kar sakte ho.

###  Example 3: Function Expression Hoisting
```bash
greet(); // ❌ TypeError: greet is not a function
var greet = function() {
  console.log("Hi");
};
```
Yahan sirf variable greet hoist hota hai (as undefined), function body nahi.

| What Gets Hoisted?   | Access Before Declaration    | Notes                          |
| -------------------- | ---------------------------- | ------------------------------ |
| `var`                | ✅ Yes (value is `undefined`) | Avoid using `var` in modern JS |
| `let` / `const`      | ❌ No (TDZ Error)             | Safer, modern way              |
| Function Declaration | ✅ Yes (fully accessible)     | Best for reusable functions    |
| Function Expression  | ❌ No                         | Treated like a `var`           |


