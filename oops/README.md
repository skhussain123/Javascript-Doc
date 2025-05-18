

# What is OOP?

OOP (Object-Oriented Programming) is a programming style that uses objects to represent data and behavior.
JavaScript supports OOP using:

Objects
Classes
Constructors
Inheritance
Encapsulation


### Object: 
An Object is a unique entity that contains properties and methods. For example “a car” is a real-life Object, which has some characteristics like color, type, model, and horsepower and performs certain actions like driving. The characteristics of an Object are called Properties in Object-Oriented Programming and the actions are called methods. An Object is an instance of a class. Objects are everywhere in JavaScript, almost every element is an Object whether it is a function, array, or string. 

Note: A Method in javascript is a property of an object whose value is a function. 
1. Object Literal
2. Object Constructor
```bash
// Defining object
let person = {
    first_name: 'Mukul',
    last_name: 'Latiyan',

    //method
    getFunction: function () {
        return (`The name of the person is 
          ${person.first_name} ${person.last_name}`)
    },
    //object within object
    phone_number: {
        mobile: '12345',
        landline: '6789'
    }
}
console.log(person.getFunction());
console.log(person.phone_number.landline);


```
Example: Using an Object Constructor.


```bash
// Using a constructor
function person(first_name, last_name) {
    this.first_name = first_name;
    this.last_name = last_name;
}
// Creating new instances of person object
let person1 = new person('Mukul', 'Latiyan');
let person2 = new person('Rahul', 'Avasthi');

console.log(person1.first_name);
console.log(`${person2.first_name} ${person2.last_name}`);

```

### Classes: 
Classes are blueprints of an Object. A class can have many Objects because the class is a template while Objects are instances of the class or the concrete implementation. 
Before we move further into implementation, we should know unlike other Object Oriented languages there are no classes in JavaScript we have only Object. To be more precise, JavaScript is a prototype-based Object Oriented Language, which means it doesn't have classes, rather it defines behaviors using a constructor function and then reuses it using the prototype



## JavaScript Object Constructors
An object is the collection of related data or functionality in the form of key. These functionalities usually consist of several functions and variables. All JavaScript values are objects except primitives. 

```bash
const GFG = {
    subject : "programming",
    language : "JavaScript",
}
```


## Object Constructor
A constructor function is a special type of function in JavaScript that is used to create and initialize objects. Constructors are used with the new keyword to create instances of a particular type (object). By using constructors, we can easily create multiple instances of the same type of object, all with their own unique properties and methods.
```bash
// Constructor function
function Person(name, age) {
    this.name = name;
    this.age = age;
    this.sayHello = function() {
        console.log(`My name is ${this.name} and I am ${this.age} years old.`);
    };
}

//Creating Instances with a Constructor
const p1 = new Person("Akash", 30);
const p2 = new Person("Anvesh", 25);

p1.sayHello();
p2.sayHello();

output:
My name is Akash and I am 30 years old.
My name is Anvesh and I am 25 years old.
```