

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



### 🔸 4. Four Pillars of OOP in JavaScript
| Pillar            | Description                                           |
| ----------------- | ----------------------------------------------------- |
| **Encapsulation** | Hides details using classes and methods.              |
| **Abstraction**   | Shows only necessary features.                        |
| **Inheritance**   | One class can use another class's properties/methods. |
| **Polymorphism**  | One method behaves differently in different classes.  |
