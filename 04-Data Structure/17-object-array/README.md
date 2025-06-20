


# What is an Object?
In JavaScript, an object is a collection of key-value pairs. These keys are also called properties or methods (if the value is a function). Objects are used to store related data and functions.
```bash
const person = {
  firstName: "John",
  lastName: "Doe",
  id: 5566,
  fullName: function() {
    return this.firstName + " " + this.lastName;
  }
};
console.log(person.fullName());

```

## JavaScript Object Constructors
A JavaScript Object Constructor is a special function used to create multiple similar objects efficiently. Think of it like a blueprint or template for making objects.

```bash
function Person(firstName, lastName, id) {
  this.firstName = firstName;
  this.lastName = lastName;
  this.id = id;
  this.fullName = function() {
    return this.firstName + " " + this.lastName;
  };
}

const person1 = new Person("John", "Doe", 101);
const person2 = new Person("Jane", "Smith", 102);

console.log(person1.fullName()); // Output: John Doe
console.log(person2.fullName()); // Output: Jane Smith


```


# JavaScript Arrays
A JavaScript array is a special variable that can hold multiple values in a single variable. Arrays are used to store lists — such as numbers, strings, or even other arrays or objects.

### 1. Using square brackets (most common):
```bash
const fruits = ["Apple", "Banana", "Mango"];
```

### 2. Using the Array constructor:
```bash
const numbers = new Array(1, 2, 3, 4);

console.log(fruits[0]); // Output: 1
console.log(fruits[2]); // Output: 3


```
### Modifying Array Elements
```bash
fruits[1] = "Orange";
console.log(fruits); // ["Apple", "Orange", "Mango"]
```

### Array Properties and Methods

| **Method**     | **Description**                                                                 | **Example**                | **Result / Notes**                        |
| -------------- | ------------------------------------------------------------------------------- | -------------------------- | ----------------------------------------- |
| `shift()`      | Removes the **first** element from an array                                     | `arr.shift()`              | Removes first item, returns it            |
| `unshift()`    | Adds one or more elements **to the beginning** of an array                      | `arr.unshift("A")`         | Adds at start, returns new length         |
| `delete`       | Deletes a specific element **without changing length** (leaves `undefined`)     | `delete arr[1]`            | Removes value but leaves an empty slot    |
| `concat()`     | Merges two or more arrays                                                       | `arr1.concat(arr2)`        | Returns a new array                       |
| `copyWithin()` | Copies part of array to another location in the **same array**                  | `arr.copyWithin(2, 0)`     | Overwrites elements starting from index 2 |
| `flat()`       | Flattens nested arrays into a single array                                      | `[1, [2, [3]]].flat(2)`    | `[1, 2, 3]`                               |
| `splice()`     | Adds/removes elements at a specific index                                       | `arr.splice(2, 1, "new")`  | Removes 1 item at index 2, adds `"new"`   |
| `toSpliced()`  | Returns a **new** array with spliced result (non-destructive version of splice) | `arr.toSpliced(1, 1, "x")` | Original stays same; new one has changes  |
| `slice()`      | Returns a portion of an array into a **new array**                              | `arr.slice(1, 3)`          | Returns elements from index 1 to 2        |
| `length`       | Returns the number of elements in the array                                     | `arr.length`               | Count of array items                      |
| `toString()`   | Converts array to a comma-separated string                                      | `arr.toString()`           | `"a,b,c"`                                 |
| `at()`         | Returns element at a specified index (supports negative index too)              | `arr.at(-1)`               | Returns last item                         |
| `join()`       | Joins array elements into a string with a separator                             | `arr.join(" - ")`          | `"a - b - c"`                             |
| `pop()`        | Removes the **last** element and returns it                                     | `arr.pop()`                | Modifies array, returns last item         |
| `push()`       | Adds one or more elements **to the end** of the array                           | `arr.push("Z")`            | Adds to end, returns new length           |


### 1. shift()
Removes the first element from the array.
```bash
const fruits = ["Apple", "Banana", "Mango"];
fruits.shift(); // Removes "Apple"
console.log(fruits); // ["Banana", "Mango"]

```

### 2. unshift()
Adds one or more elements to the beginning of the array.
```bash
const fruits = ["Banana", "Mango"];
fruits.unshift("Apple");
console.log(fruits); // ["Apple", "Banana", "Mango"]

```

### 3. delete
Deletes a specific element by index (leaves undefined at that index).
```bash
const fruits = ["Apple", "Banana", "Mango"];
delete fruits[1];
console.log(fruits); // ["Apple", undefined, "Mango"]
```

### 4. concat()
Merges two or more arrays into a new array.
```bash
const arr1 = [1, 2];
const arr2 = [3, 4];
const result = arr1.concat(arr2);
console.log(result); // [1, 2, 3, 4]
```

### 5. copyWithin()
Copies part of the array within itself.
```bash
const arr = [1, 2, 3, 4];
arr.copyWithin(2, 0); // Copy elements from index 0 to index 2
console.log(arr); // [1, 2, 1, 2]
```

### 6. flat()
Flattens a nested array.
```bash
const arr = [1, [2, [3, 4]]];
const flatArr = arr.flat(2);
console.log(flatArr); // [1, 2, 3, 4]

```

### 7. splice()
Adds/removes items in the array.
```bash
const arr = ["a", "b", "c", "d"];
arr.splice(1, 2, "x", "y"); // Remove 2 items from index 1 and add "x", "y"
console.log(arr); // ["a", "x", "y", "d"]
```

### 8. toSpliced() (New ES2023)
Returns a new array after splice operation (original is not changed).
```bash
const arr = ["a", "b", "c", "d"];
const newArr = arr.toSpliced(1, 2, "x", "y");
console.log(newArr); // ["a", "x", "y", "d"]
console.log(arr);    // ["a", "b", "c", "d"]  ← original remains unchanged

```

### 9. slice()
Returns a portion of the array.
```bash
const arr = ["a", "b", "c", "d"];
const sliced = arr.slice(1, 3);
console.log(sliced); // ["b", "c"]

```

### 10. length
Returns the number of elements in the array.
```bash
const arr = [10, 20, 30];
console.log(arr.length); // 3

```

### 11. toString()
Converts array to a comma-separated string.
```bash
const arr = [1, 2, 3];
console.log(arr.toString()); // "1,2,3"

```

### 12. at()
Returns element at a given index, supports negative indexing.
```bash
const arr = ["a", "b", "c"];
console.log(arr.at(-1)); // "c" (last item)

```

### 13. join()
Joins array items into a string with custom separator.
```bash
const arr = ["a", "b", "c"];
console.log(arr.join(" - ")); // "a - b - c"

```

### 14. pop()
Removes the last element and returns it.
```bash
const arr = [1, 2, 3];
arr.pop(); // Removes 3
console.log(arr); // [1, 2]

```

### 15. push()
Adds one or more items to the end of the array.
```bash
const arr = [1, 2];
arr.push(3, 4);
console.log(arr); // [1, 2, 3, 4]
```


## JavaScript Array Search

| Method            | Returns              | What it Finds                  |
| ----------------- | -------------------- | ------------------------------ |
| `find()`          | First matching value | Based on a condition           |
| `findIndex()`     | Index of first match | Based on a condition           |
| `findLast()`      | Last matching value  | Based on a condition           |
| `findLastIndex()` | Index of last match  | Based on a condition           |
| `indexOf()`       | Index of value       | First match of a given value   |
| `lastIndexOf()`   | Index of value       | Last match of a given value    |
| `includes()`      | `true` or `false`    | If a value exists in the array |

### 1. find()
🔍 Finds the first element that matches a condition.
```bash
const numbers = [10, 20, 30, 40];
const result = numbers.find(num => num > 25);
console.log(result); // 30

```

### 2. findIndex()
🔢 Finds the index of the first element that matches a condition.
```bash
const numbers = [10, 20, 30, 40];
const index = numbers.findIndex(num => num > 25);
console.log(index); // 2
```

### 3. findLast() (New ES2023)
🔍 Finds the last element that matches a condition.
```bash
const numbers = [10, 20, 30, 40];
const result = numbers.findLast(num => num > 15);
console.log(result); // 40
```

### 4. findLastIndex() (New ES2023)
🔢 Finds the index of the last matching element.
```bash
const numbers = [10, 20, 30, 40];
const index = numbers.findLastIndex(num => num > 15);
console.log(index); // 3

```

### 5. indexOf()
🔢 Returns the first index of a specific value.
```bash
const fruits = ["apple", "banana", "mango", "banana"];
console.log(fruits.indexOf("banana")); // 1
```

### 6. lastIndexOf()
🔢 Returns the last index of a specific value.
```bash
const fruits = ["apple", "banana", "mango", "banana"];
console.log(fruits.lastIndexOf("banana")); // 3
```

### 7. includes()
✅ Checks if a value exists in the array (true/false).
```bash
const fruits = ["apple", "banana", "mango"];
console.log(fruits.includes("banana")); // true
console.log(fruits.includes("grape"));  // false

```


# JavaScript Array Sorting Methods 
| Method           | Description                               | Mutates Original? |
| ---------------- | ----------------------------------------- | ----------------- |
| `sort()`         | Sorts array alphabetically or numerically | ✅ Yes             |
| `reverse()`      | Reverses array                            | ✅ Yes             |
| `toSorted()`     | Sorted copy (ES2023)                      | ❌ No              |
| `toReversed()`   | Reversed copy (ES2023)                    | ❌ No              |
| `Math.min()`     | Gets smallest number                      | ❌ No              |
| `Math.max()`     | Gets largest number                       | ❌ No              |
| `sort(a-b)`      | Numeric sort                              | ✅ Yes             |
| `sort(()=>rand)` | Random sort (not guaranteed)              | ✅ Yes             |
| Custom loop      | Home-made min/max                         | ✅ N/A             |


### 🔹 1. sort()
Sorts array alphabetically (by default) or numerically (with custom logic).
```bash
const fruits = ["Banana", "Apple", "Mango"];
fruits.sort();
console.log(fruits); // ["Apple", "Banana", "Mango"]

```
**Numeric sort (default fails!):**
```bash
const nums = [10, 2, 30];
nums.sort(); // Incorrect result: [10, 2, 30] → treated as strings
```

**Correct numeric sort:**
```bash
nums.sort((a, b) => a - b);
console.log(nums); // [2, 10, 30]
```

### 🔹 2. reverse()
Reverses the array in place.
```bash
const arr = [1, 2, 3];
arr.reverse();
console.log(arr); // [3, 2, 1]

```

### 🔹 3. toSorted() (✅ ES2023)
Returns a new sorted array, original stays unchanged.
```bash
const nums = [5, 3, 1];
const sorted = nums.toSorted((a, b) => a - b);
console.log(sorted);  // [1, 3, 5]
console.log(nums);    // [5, 3, 1]
```

### 🔹 4. toReversed() (✅ ES2023)
Returns a new reversed array without changing the original.
```bash
const arr = [1, 2, 3];
const reversed = arr.toReversed();
console.log(reversed); // [3, 2, 1]
console.log(arr);      // [1, 2, 3]
```

### 5. Sorting Objects Numerically
```bash
const people = [
  { name: "Ali", age: 30 },
  { name: "Sara", age: 22 },
  { name: "Zain", age: 27 }
];

people.sort((a, b) => a.age - b.age);
console.log(people); // Sorted by age: Sara, Zain, Ali
```

###  6. Random Sort (⚠️ Not 100% reliable)
```bash
const arr = [1, 2, 3, 4, 5];
arr.sort(() => 0.5 - Math.random());
console.log(arr); // Random order
```

### 7. Math.min() and Math.max()
Finds smallest/largest numbers.
```bash
const nums = [10, 5, 3, 99];
console.log(Math.min(...nums)); // 3
console.log(Math.max(...nums)); // 99
```

### 🔹 8. Home Made min() and max()
Manually find the minimum and maximum without using Math methods.
```bash
const nums = [10, 5, 3, 99];

// Homemade Min
let min = nums[0];
for (let num of nums) {
  if (num < min) min = num;
}
console.log(min); // 3

// Homemade Max
let max = nums[0];
for (let num of nums) {
  if (num > max) max = num;
}
console.log(max); // 99
```

# JavaScript Array Iteration Methods
| Method          | Description                               | Returns New Array? |
| --------------- | ----------------------------------------- | ------------------ |
| `forEach()`     | Loops over items                          | ❌ No               |
| `map()`         | Transforms each item                      | ✅ Yes              |
| `flatMap()`     | Map + flatten                             | ✅ Yes              |
| `filter()`      | Keeps items that pass test                | ✅ Yes              |
| `reduce()`      | Reduces to a single value (left to right) | ❌ No               |
| `reduceRight()` | Reduces right to left                     | ❌ No               |
| `every()`       | Checks if **all** match condition         | ❌ No (true/false)  |
| `some()`        | Checks if **any** match condition         | ❌ No (true/false)  |
| `from()`        | Converts iterable to array                | ✅ Yes              |
| `keys()`        | Iterator of indexes                       | ❌ No               |
| `entries()`     | Iterator of \[index, value] pairs         | ❌ No               |
| `with()`        | Replace 1 item, return new array          | ✅ Yes (ES2023)     |
| `...spread`     | Expands elements                          | ✅ Yes              |


### 🔹 1. forEach()
Loops through each element of the array.
```bash
const nums = [1, 2, 3];
nums.forEach((num, index) => {
  console.log(`Index ${index}: ${num}`);
});

```

### 🔹 2. map()
Creates a new array by transforming each element.
```bash
const nums = [1, 2, 3];
const doubled = nums.map(num => num * 2);
console.log(doubled); // [2, 4, 6]
```

### 🔹 3. flatMap()
Maps each element and then flattens one level.
```bash
const arr = ["one", "two"];
const result = arr.flatMap(word => word.split(""));
console.log(result); // ["o", "n", "e", "t", "w", "o"]
```

### 🔹 4. filter()
Creates a new array with only elements that pass a test.
```bash
const nums = [10, 20, 30];
const filtered = nums.filter(num => num > 15);
console.log(filtered); // [20, 30]
```

### 🔹 5. reduce()
Reduces the array to a single value (left to right).
```bash
const nums = [1, 2, 3, 4];
const sum = nums.reduce((acc, val) => acc + val, 0);
console.log(sum); // 10
```

### 🔹 6. reduceRight()
Same as reduce() but starts from the right side.
```bash
const nums = [1, 2, 3, 4];
const result = nums.reduceRight((acc, val) => acc - val);
console.log(result); // (((4 - 3) - 2) - 1) = -2
```

### 🔹 7. every()
Checks if all elements pass a test → returns true or false.
```bash
const nums = [10, 20, 30];
const allAbove5 = nums.every(num => num > 5);
console.log(allAbove5); // true
```

### 🔹 8. some()
Checks if any one element passes the test.
```bash
const nums = [1, 2, 3];
const hasEven = nums.some(num => num % 2 === 0);
console.log(hasEven); // true
```

### 🔹 9. from()
Creates an array from any iterable (like a string).
```bash
const str = "hello";
const arr = Array.from(str);
console.log(arr); // ["h", "e", "l", "l", "o"]
```

### 🔹 10. keys()
Returns an iterator of array indices.
```bash
const fruits = ["Apple", "Banana"];
const keys = fruits.keys();
for (let key of keys) {
  console.log(key); // 0, 1
}

```

### 🔹 11. entries()
Returns an iterator of [index, value] pairs.
```bash
const fruits = ["Apple", "Banana"];
for (let [index, value] of fruits.entries()) {
  console.log(index, value); // 0 "Apple", 1 "Banana"
}

```

### 🔹 12. with() (ES2023)
Returns a new array with one element replaced (original is not changed).
```bash
const nums = [1, 2, 3];
const newArr = nums.with(1, 99); // replace index 1 with 99
console.log(newArr); // [1, 99, 3]

```

### 13. Spread Syntax ...
Spreads array elements individually.
```bash
const arr1 = [1, 2];
const arr2 = [...arr1, 3, 4];
console.log(arr2); // [1, 2, 3, 4]
```
