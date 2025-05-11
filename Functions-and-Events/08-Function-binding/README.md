


# JavaScript Function Binding
JavaScript Function Binding ka matlab hai this keyword ko fix karna, taa keh function jab bhi chale, wo sahi object ke sath hi kaam kare.

## Ye this kya hota hai?
this ka matlab hota hai:

**"Ye function kis object ka hissa hai?"**

Agar this galat object ko point kare, to function ghalat kaam karega ya error dega. Binding se hum this ko lock kar dete hain.

## Q Use Hota Hai?
Kabhi kabhi function apni jagah change kar leta hai (like event ya setTimeout mein), to this kho jata hai. Binding use karte hain taa keh:

* Function ko sahi object ke sath joda ja sake.
* this ki value confuse na ho.
* Callback ya event handlers mein problem na aaye.

## 1: bind() Example

```bash
const user = {
  name: "Ali",
  greet: function() {
    console.log("Hello " + this.name);
  }
};

const greetFunc = user.greet;
greetFunc(); // ❌ this.name is undefined


const greetFuncBound = user.greet.bind(user);
greetFuncBound(); // ✅ Hello Ali


```

## 2: call() Example
```bash
function introduce(city, country) {
  console.log("My name is " + this.name + " and I live in " + city + ", " + country);
}

const person = { name: "Ali" };

introduce.call(person, "Lahore", "Pakistan");
// Output: My name is Ali and I live in Lahore, Pakistan

```
* Yahan call() ne introduce function ko foran chalaya aur this ko person banaya.
* Arguments directly diye: "Lahore", "Pakistan"

## 3: apply() Example
```bash
function introduce(city, country) {
  console.log("My name is " + this.name + " and I live in " + city + ", " + country);
}

const person = { name: "Ali" };

introduce.apply(person, ["Karachi", "Pakistan"]);
// Output: My name is Ali and I live in Karachi, Pakistan
```
apply() bhi same kaam karta hai, lekin arguments array mein pass hote hain: ["Karachi", "Pakistan"]

