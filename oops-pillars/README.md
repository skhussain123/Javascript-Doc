

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
