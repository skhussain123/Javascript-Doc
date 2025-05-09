

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


# **Data Types**
JavaScript supports various datatypes, which can be broadly categorized into primitive and non-primitive types.

* Primitive Datatypes
* Non-Primitive Datatypes


### **Primitive Datatypes**
Primitive datatypes represent single values and are immutable.

**1. Number: Represents numeric values (integers and decimals).**
The Number data type in JavaScript includes both integers and floating-point numbers. Special values like Infinity, -Infinity, and NaN represent infinite values and computational errors, respectively.

```bash
let n1 = 2;
console.log(n1)

let n2 = 1.3;
console.log(n2)

let n3 = Infinity;
console.log(n3)

let n4 = 'something here too' / 2;
console.log(n4)

OUT:
2
1.3
Infinity
NaN
```

**2. String: Represents text enclosed in single or double quotes.**
A String in JavaScript is a series of characters that are surrounded by quotes. There are three types of quotes in JavaScript, which are.
```bash
let s1 = "Hello There";
console.log(s1); 

let s2 = 'Single quotes work fine';
console.log(s2); 

let s3 = `can embed ${s1}`;
console.log(s3);

out: 
Hello There
Single quotes work fine
can embed Hello There
```

**3. Boolean: Represents a logical value (true or false).**
```bash
let b1 = true;
console.log(b1);  

let b2 = false;
console.log(b2);

out:
true
false
```

**4. Undefined: A variable that has been declared but not assigned a value.**
```bash
let notAssigned;
console.log(notAssigned);

output:
undefined
```

**5. Null: Represents an intentional absence of any value.**
The special null value does not belong to any of the default data types. It forms a separate type of its own which contains only the null value.
```bash
let age = null;
console.log(age)

out:
null
```

**6. Symbol: Represents unique and immutable values, often used as object keys. (Introduced in ES6)**
Symbols, introduced in ES6, are unique and immutable primitive values used as identifiers for object properties. They help create unique keys in objects, preventing conflicts with other properties.
```bash
let s1 = Symbol("Geeks");
let s2 = Symbol("Geeks");
console.log(s1 == s2);

out:
false
```

**7. BigInt: Represents integers larger than Number.MAX_SAFE_INTEGER.**
BigInt is a built-in object that provides a way to represent whole numbers greater than 253. The largest number that JavaScript can reliably represent with the Number primitive is 253, which is represented by the MAX_SAFE_INTEGER constant.
```bash
let b = BigInt("0b1010101001010101001111111111111111");
console.log(b);

output:
11430854655
```

### **Non-Primitive Datatypes**
Non-primitive types are objects and can store collections of data or more complex entities.

**1. Object: Represents key-value pairs.**
JavaScript objects are key-value pairs used to store data, created with {} or the new keyword. They are fundamental as nearly everything in JavaScript is an object.
```bash
let gfg = {
    type: "Company",
    location: "Noida"
}
console.log(gfg.type)

out:
Company
```

**2. Array: Represents an ordered list of values.**
An Array is a special kind of object used to store an ordered collection of values, which can be of any data type.

```bash
let a1 = [1, 2, 3, 4, 5];
console.log(a1);

let a2 = [1, "two", { name: "Object" }, [3, 4, 5]];
console.log(a2);

output:
[ 1, 2, 3, 4, 5 ]
[ 1, 'two', { name: 'Object' }, [ 3, 4, 5 ] ]
```

**3. Function: Represents reusable blocks of code.**
A function in JavaScript is a block of reusable code designed to perform a specific task when called.

```bash
// Defining a function to greet a user
function greet(name) { return "Hello, " + name + "!"; }
// Calling the function
console.log(greet("Ajay"));

output:
Hello, Ajay!
```


### **4. Date Object**
The Date object in JavaScript is used to work with dates and times, allowing for date creation, manipulation, and formatting.
```bash
// Creating a new Date object for the current date and time
let currentDate = new Date();
// Displaying the current date and time
console.log(currentDate);

output:
2025-03-08T06:23:33.202Z
```

### **5. Regular Expression**
A RegExp (Regular Expression) in JavaScript is an object used to define search patterns for matching text in strings
```bash
// Creating a regular expression to match the word "hello"
let pattern = /hello/;
// Testing the pattern against a string
let result = pattern.test("Hello, world!"); // Returns true because "Hello" matches the pattern
console.log(result);

output:
false
```


# **Interesting Facts about Data Types**
## **1. Dynamically Typed :** JavaScript Variables are not bound to a specific data type. Mainly data type is stored with value (not with variable name) and is decided & checked at run time.
```bash
// Creating a regular expression to match the word "hello"
let pattern = /hello/;
// Testing the pattern against a string
let result = pattern.test("Hello, world!"); // Returns true because "Hello" matches the pattern
console.log(result);

output:
false
```

# **Interesting Facts about Data Types**
## **1. Dynamically Typed :** JavaScript Variables are not bound to a specific data type. Mainly data type is stored with value (not with variable name) and is decided & checked at run time.
```bash
let x = 42;   
console.log(x)

x = "hello";  
console.log(x)

x = [1, 2, 3]
console.log(x)

output:
42
hello
[ 1, 2, 3 ]
```

## 2. Everything is an Object (Sort of): 
In JavaScript, Functions are objects, arrays are objects, and even primitive values can behave like objects temporarily when you try to access properties on them.
```bash
let s = "hello";
console.log(s.length);  

// Example with a number
let x = 42;
console.log(x.toString()); 

// Example with a boolean
let y = true;
console.log(y.toString());

/* Internal Working of primitives
   to be treeated as objects
   
// Temporary wrapper object
let temp = new String("hello"); 

console.log(temp.length); // 5

// The wrapper is discarded after use
temp = null; */

output:
5
42
true
```

## **3. NaN is not equal to itself:** 
NaN Stands for “Not-a-Number”, It is used to represent a computational error. NaN is technically of type number.
```bash
console.log(typeof NaN);
console.log(NaN === NaN);

output:
number
false
```

## **4. A Symbol is Never Equal to Another One :** 
Symbol is a unique and immutable data type often used for creating private properties and methods. Symbols are never equal to any other Symbol.
```bash
let s1 = Symbol("abc");
let s2 = Symbol("abc");
console.log(s1 === s2);

output:
false
```

## **5. Undefined and Null:** 
undefined represents a variable that has been declared but not assigned, while null is an explicit assignment representing “no value”.

## **6. Integers are Floating are Numbers only**
There is only one type number that covers both integers and floating point numbers.
```bash
let x = 42;     // Integer
let y = 42.5;   // Floating-point

console.log(typeof x); 
console.log(typeof y);

output:
number
number

```

## **7. A character is also a string.** 
There is no separate type for characters. A single character is also a string.
```bash
let s1 = "gfg";   // String
let s2 = 'g';    // Character

console.log(typeof s1); 
console.log(typeof s2);

output:
string
string
```