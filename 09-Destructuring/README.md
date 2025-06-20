

#  JavaScript Destructuring – Simple Explanation with Examples
Destructuring is a way to unpack values from arrays or objects into separate variables.

### 1. Array Destructuring
```bash
const numbers = [10, 20, 30];
const [a, b, c] = numbers;

console.log(a); // 10
console.log(b); // 20
console.log(c); // 30

```

**Skip values**
```bash
const [first, , third] = [1, 2, 3];
console.log(first, third); // 1 3
```

### 2. Object Destructuring
```bash
const person = {
  name: "Ali",
  age: 25,
  city: "Lahore"
};

const { name, age } = person;
console.log(name); // Ali
console.log(age);  // 25

```

**Rename Variables**
```bash
const { name: userName } = person;
console.log(userName); // Ali
```

### 3. Default Values
```bash
const { country = "Pakistan" } = person;
console.log(country); // Pakistan
```

```bash
const [x = 1, y = 2] = [];
console.log(x, y); // 1 2
```

### 4. Nested Destructuring
```bash
const user = {
  info: {
    email: "ali@example.com"
  }
};

const {
  info: { email }
} = user;

console.log(email); // ali@example.com

```

### 5. Destructure in Function Parameters
```bash
function greet({ name, age }) {
  console.log(`Hello ${name}, age ${age}`);
}

const person = { name: "Sara", age: 22 };
greet(person); // Hello Sara, age 22
```

### 6. Destructuring with Rest (...)
```bash
const [first, ...rest] = [1, 2, 3, 4];
console.log(first); // 1
console.log(rest);  // [2, 3, 4]

```

```bash
const { name, ...others } = { name: "Ali", age: 25, city: "Lahore" };
console.log(others); // { age: 25, city: "Lahore" }
```