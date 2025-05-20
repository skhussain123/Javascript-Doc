

## 🔹 What is OOP?
Object-Oriented Programming is a way to organize your code using objects, which group data (properties) and functions (methods) together.

* A Class is like a blueprint or template for creating objects.
* It defines properties (data) and methods (functions) that the objects created from this class will have.
* Think of a class as a plan or design, like a blueprint for a house.


### 📘 What is an Object?

* An Object is an instance of a class.
* It is a real thing created using the blueprint (class).
* Each object has its own values for properties defined by the class.


### 🔸 1. What is an Object?
```bash
let student = {
  name: "Ali",
  age: 22,
  greet: function () {
    console.log("Hello, my name is " + this.name);
  }
};

student.greet(); // Output: Hello, my name is Ali

```

### 🔸 2. Object with Constructor Function

```bash
function Student(name, age) {
  this.name = name;
  this.age = age;
  this.greet = function () {
    console.log("Hi, I am " + this.name);
  };
}

let s1 = new Student("Ali", 22);
s1.greet(); // Hi, I am Ali

```

### 🔸 3. Class in JavaScript (ES6+)

```bash
class Student {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  greet() {
    console.log(`Hello, I’m ${this.name}`);
  }
}

let std1 = new Student("Zain", 23);
std1.greet();

```

## 📘 1. Class Properties (Data Members)
Class properties are the variables that store data inside a class.

```bash
class Student {
  constructor(name, age) {
    this.name = name;  // property
    this.age = age;    // property
  }
}

```
**this.name and this.age → are class properties**


## 📘 2. Class Methods (Functions)
Class methods are the functions defined inside a class that perform actions.

```bash
class Student {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  // This is a class method
  introduce() {
    console.log(`My name is ${this.name} and I am ${this.age} years old.`);
  }
}

let std = new Student("Ali", 21);
std.introduce();  // Method call

```



## 🔹 Types of Methods in JavaScript Classes

### 1. Instance Methods:

* These are regular methods defined inside the class.
* They operate on individual instances (objects) of the class.
* Can access instance properties via this.

```bash
class Person {
  constructor(name) {
    this.name = name;
  }
  
  greet() {
    console.log(`Hello, my name is ${this.name}`);
  }
}

let p = new Person("Ali");
p.greet();  // Hello, my name is Ali


```

### 2. Static Methods

* Belong to the class itself, not instances.
* Called using the class name, not the object.
* Useful for utility or helper functions.

```bash
class MathHelper {
  static square(x) {
    return x * x;
  }
}

console.log(MathHelper.square(5));  // 25

```

### 3. Getter Methods

* Special methods that get the value of a property.
* Used as properties but implemented as functions.
* Defined with get keyword.

```bash
class Rectangle {
  constructor(width, height) {
    this.width = width;
    this.height = height;
  }
  
  get area() {
    return this.width * this.height;
  }
}

let rect = new Rectangle(5, 4);
console.log(rect.area);  // 20 (called like a property, not function)

```

### 4. Setter Methods

* Special methods that set the value of a property.
* Defined with set keyword.
* Used for validation or controlling how properties are set.

```bash
class Person {
  set age(value) {
    if (value < 0) {
      console.log("Age can't be negative");
    } else {
      this._age = value;
    }
  }
  
  get age() {
    return this._age;
  }
}

let p = new Person();
p.age = 25;
console.log(p.age);  // 25
p.age = -5;          // Age can't be negative

```

### 5. Async Methods

* Methods that return a Promise.
* Use async keyword and can use await inside.
* Useful for asynchronous operations.

```bash
class DataFetcher {
  async fetchData() {
    let response = await fetch('https://api.example.com/data');
    let data = await response.json();
    return data;
  }
}

let fetcher = new DataFetcher();
fetcher.fetchData().then(data => console.log(data));
```

| Method Type | Description                       | Called On        | Syntax Example            |
| ----------- | --------------------------------- | ---------------- | ------------------------- |
| Instance    | Normal method for each object     | Object instances | `obj.method()`            |
| Static      | Belongs to class, utility methods | Class itself     | `ClassName.method()`      |
| Getter      | Access property like a variable   | Object instances | `obj.property`            |
| Setter      | Set property with validation      | Object instances | `obj.property = value`    |
| Async       | Handles asynchronous code         | Object instances | `await obj.asyncMethod()` |


