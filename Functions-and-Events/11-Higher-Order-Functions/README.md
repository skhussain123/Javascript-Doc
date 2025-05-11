

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
The callback (num) => num > 0 checks if all numbers are positive.
It returns true only if all elements pass the condition.


