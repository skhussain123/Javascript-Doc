

# **Variables and Datatypes in JavaScript**
Variables and data types are foundational concepts in programming, serving as the building blocks for storing and manipulating information within a program. In JavaScript, getting a good grasp of these concepts is important for writing code that works well and is easy to understand.

## **Variables**
A variable is like a container that holds data that can be reused or updated later in the program. In JavaScript, variables are declared using the keywords var, let, or const.


### **1. var Keyword**
The var keyword is used to declare a variable. It has a function-scoped or globally-scoped behaviour.
```bash
var n = 5;
console.log(n);

var n = 20; // reassigning is allowed
console.log(n);
```


### **2. let Keyword**
The let keyword is introduced in ES6, has block scope and cannot be re-declared in the same scope.
```bash
let  n= 10;
n = 20; // Value can be updated
// let n = 15; //can not redeclare
console.log(n)
```


### **3. const Keyword**
The const keyword declares variables that cannot be reassigned. It’s block-scoped as well.
```bash
const n = 100;
// n = 200; This will throw an error
console.log(n)
```
