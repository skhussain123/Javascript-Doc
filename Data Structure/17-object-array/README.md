


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