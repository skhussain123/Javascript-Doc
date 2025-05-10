


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


### **Return Statement**
In some situations, we want to return some values from a function after performing some operations. In such cases, we make use of the return. This is an optional statement. In the above function, “sum()” returns the sum of two as a result. 
```bash
# Define a function that returns the sum of two numbers
var a;
var b;

def sum():
    result = a + b
    return result

# Call the function and store the result
total = sum(5, 3)

# Print the result
print("The sum is:", total)

Output:
The sum is: 8

```
### **Function Parameters**

Parameters are inputs passed to a function so it can perform operations using those values. In the example below, the sum() function takes two parameters, x and y, and returns their sum.
```bash
# Define a function with parameters x and y
def sum(x, y):
    return x + y

# Call the function with arguments
result = sum(10, 20)

print("The result is:", result)
```
