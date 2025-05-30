

### 🔸 Four Pillars of OOP in JavaScript
| Pillar            | Description                                           |
| ----------------- | ----------------------------------------------------- |
| **Encapsulation** | Hides details using classes and methods.              |
| **Abstraction**   | Shows only necessary features.                        |
| **Inheritance**   | One class can use another class's properties/methods. |
| **Polymorphism**  | One method behaves differently in different classes.  |


### 📘 What is Inheritance?

* Inheritance allows a class (child class) to reuse the properties and methods of another class (parent class).
* It helps in code reusability, organization, and supports the concept of "is-a" relationship.

```bash
class Parent {
  constructor() {
    console.log("Parent constructor");
  }

  greet() {
    console.log("Hello from Parent");
  }
}

class Child extends Parent {
  constructor() {
    super(); // Call the parent constructor
    console.log("Child constructor");
  }

  speak() {
    console.log("Hello from Child");
  }
}

let obj = new Child();
obj.greet();  // Inherited method from Parent
obj.speak();  // Child's own method


```

**🔸 extends Keyword**

* Used to make a class inherit from another class.
* Child extends Parent means the Child class now gets all the methods and properties of the Parent class.


**🔸 super() Keyword**

* Used to call the parent class’s constructor or methods.
* Must be called before using this in the constructor.

```bash
class Animal {
  constructor(name) {
    this.name = name;
  }

  makeSound() {
    console.log(`${this.name} makes a sound`);
  }
}

class Dog extends Animal {
  constructor(name, breed) {
    super(name);  // Call Animal's constructor
    this.breed = breed;
  }

  bark() {
    console.log(`${this.name} barks`);
  }
}

let dog1 = new Dog("Max", "Labrador");

dog1.makeSound();  // Max makes a sound
dog1.bark();       // Max barks

```

### 🔑 Types of Inheritance in JavaScript

1. Single Inheritance
2. Multilevel Inheritance
3. Hierarchical Inheritance
4. Multiple Inheritance (not supported directly)
5. Hybrid Inheritance (Combination of two or more types)


### 1. Single Inheritance
In single inheritance, a child class inherits from only one parent class.
Supported in JavaScript (via class or prototype).

```bash
class Animal {
  speak() {
    console.log("Animal speaks");
  }
}

class Dog extends Animal {}

const d = new Dog();
d.speak(); // Inherited from Animal

```

### 2. Multilevel Inheritance
In this type, a class inherits from a class which is already a child of another class — forming a chain.

```bash
class A {
  methodA() {
    console.log("A");
  }
}

class B extends A {
  methodB() {
    console.log("B");
  }
}

class C extends B {
  methodC() {
    console.log("C");
  }
}

```

### 3. Hierarchical Inheritance
A single parent class is inherited by multiple child classes.
Supported in JavaScript.

```bash
class Parent {
  greet() {
    console.log("Hello from Parent");
  }
}

class Child1 extends Parent {}
class Child2 extends Parent {}

```

### 4. Multiple Inheritance (Not Supported Directly)
In multiple inheritance, a class inherits from more than one parent class.
🔴 Not directly supported in JavaScript.
🟡 Can be achieved using mixins.

```bash
let Fly = {
  fly() { console.log("Flying"); }
};

let Swim = {
  swim() { console.log("Swimming"); }
};

class Animal {}

Object.assign(Animal.prototype, Fly, Swim);

```

### 5. Hybrid Inheritance
This is a combination of two or more types of inheritance (e.g., hierarchical + multilevel).
Can be simulated using mixins and class extensions in JavaScript.

Note: JavaScript doesn’t support true hybrid inheritance due to lack of direct multiple inheritance, but you can simulate it with careful design.



## 2. Encapsulation
Encapsulation is one of the core concepts of Object-Oriented Programming (OOP). It refers to hiding internal details of an object and only exposing a controlled interface. In simple terms, it's about bundling data and methods that operate on that data into a single unit (object), and restricting direct access to some of the object's components.

* Protects data from being modified directly.
* Makes code more secure, organized, and maintainable.
* Allows you to control access via getters and setters.


JavaScript supports encapsulation in several ways:

### 🔹 1. Using Closures (Pre-ES6 way)
```bash
function Person(name) {
  let _name = name; // private variable

  this.getName = function () {
    return _name;
  };

  this.setName = function (newName) {
    if (newName.length > 0) {
      _name = newName;
    }
  };
}

const p = new Person("Ali");
console.log(p.getName()); // Ali
p.setName("Zara");
console.log(p.getName()); // Zara

```

### 🔹 2. Using ES6 class + Private Fields (#)
```bash
class Person {
  #name; // private field

  constructor(name) {
    this.#name = name;
  }

  getName() {
    return this.#name;
  }

  setName(newName) {
    if (newName.length > 0) {
      this.#name = newName;
    }
  }
}

const p = new Person("Ali");
console.log(p.getName()); // Ali
p.setName("Zara");
console.log(p.getName()); // Zara
// console.log(p.#name); // ❌ Error: private field

```

### 🔹 3. Using Getters and Setters
```bash
class Product {
  #price;

  constructor(price) {
    this.#price = price;
  }

  get price() {
    return this.#price;
  }

  set price(value) {
    if (value > 0) {
      this.#price = value;
    } else {
      console.log("Invalid price");
    }
  }
}

const item = new Product(100);
console.log(item.price); // 100
item.price = 200;
console.log(item.price); // 200
item.price = -50;        // Invalid price

```

## 3. Polymorphism in JavaScript
Polymorphism means “many forms.” In JavaScript, polymorphism allows objects to share the same method name but behave differently depending on their type or class.


### Types of Polymorphism in JavaScript

#### 1. Function Overriding (Runtime Polymorphism)
* When a child class redefines a method of its parent class.
* Most common type of polymorphism in JavaScript.

```bash
class Animal {
  speak() {
    console.log("The animal makes a sound");
  }
}

class Dog extends Animal {
  speak() {
    console.log("The dog barks");
  }
}

class Cat extends Animal {
  speak() {
    console.log("The cat meows");
  }
}

const animals = [new Animal(), new Dog(), new Cat()];
animals.forEach(animal => animal.speak());


output:
The animal makes a sound  
The dog barks  
The cat meows

```

#### 2. Function Overloading (Not native in JS)
JavaScript doesn’t support function overloading directly like other languages (Java, C++), but you can mimic it using:

```bash
function greet(name, age) {
  if (age === undefined) {
    console.log(`Hello, ${name}`);
  } else {
    console.log(`Hello, ${name}. You are ${age} years old.`);
  }
}

greet("Ali");
greet("Ahmed", 25);

output:
Hello, Ali  
Hello, Ahmed. You are 25 years old.


```

#### Why Use Polymorphism?
* Cleaner code
* Easier to scale
* Enables inheritance and code reuse
* Supports OOP principles


#### Real-World Example
```bash

class Shape {
  draw() {
    console.log("Drawing a shape");
  }
}

class Circle extends Shape {
  draw() {
    console.log("Drawing a circle");
  }
}

class Rectangle extends Shape {
  draw() {
    console.log("Drawing a rectangle");
  }
}

function render(shape) {
  shape.draw(); // Polymorphic behavior
}

render(new Shape());
render(new Circle());
render(new Rectangle());

```

| Concept              | In JS? | Example Type             |
| -------------------- | ------ | ------------------------ |
| Function Overriding  | ✅ Yes  | Class inheritance        |
| Function Overloading | ❌ No\* | Can be mimicked manually |


## 4. Abstraction in JavaScript
Abstraction means hiding the complex internal details and showing only the essential features to the user.

#### Real-Life Example:

* Jab aap car chala rahe ho, aap sirf steering, accelerator, brake dekhte ho.
* Aapko andar ka engine kaise kaam karta hai — uski detail hide hoti hai.
* That’s abstraction!

JavaScript doesn’t have pure abstraction classes like Java/C++, but we can still implement abstraction using:

* Classes + Methods
* Encapsulation (using private properties)
* Interfaces (mimicked using objects + functions)

### Basic Abstraction Using Class
```bash
class Car {
  constructor() {
    this._speed = 0; // underscore means “private” by convention
  }

  accelerate() {
    this._speed += 10;
    console.log(`Accelerating... Current speed: ${this._speed}`);
  }

  brake() {
    this._speed -= 5;
    console.log(`Braking... Current speed: ${this._speed}`);
  }
}

const car = new Car();
car.accelerate();
car.brake();

```
User doesn't know how speed is calculated internally — they just use accelerate() and brake().

### Modern JS: Private Fields for Real Abstraction
Since ES2022, JavaScript allows private fields using

```bash
class BankAccount {
  #balance = 0;

  deposit(amount) {
    this.#balance += amount;
  }

  getBalance() {
    return this.#balance;
  }
}

const account = new BankAccount();
account.deposit(1000);
console.log(account.getBalance()); // ✅ 1000
console.log(account.#balance); // ❌ Error: Private field

```

| Concept      | In JavaScript?                          | How to Use                        |
| ------------ | --------------------------------------- | --------------------------------- |
| Abstraction  | ✅ Yes                                   | Classes, private fields, methods  |
| Hide details | ✅                                       | `#` fields, underscore convention |
| User access  | ✅ Only what is exposed (public methods) |                                   |
