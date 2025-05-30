

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