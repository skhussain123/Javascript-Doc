


# JavaScript Hoisting

"JavaScript aapke code ke kuch hisso ko automatically upar le jata hai execution se pehle."

* Variables (using var)
* Function declarations ko JavaScript pehle hi memory mein store kar leta hai function ya scope ke start mein, chahe aap ne neeche likha ho.


### Example 1: Variable Hoisting (using var)
```bash
console.log(x); // undefined
var x = 5;

```
**Yahan JavaScript isay aise samajhti hai:**
```bash
var x;
console.log(x); // undefined
x = 5;

```
Note: let aur const hoist to hote hain, lekin unka access pehle nahi milta (TDZ error deta hai).

### Example 2: Function Hoisting
```bash
greet(); // Hello!
function greet() {
  console.log("Hello!");
}

```
JavaScript is function ko poora upar le jata hai — is liye aap use pehle bhi call kar sakte ho.

###  Example 3: Function Expression Hoisting
```bash
greet(); // ❌ TypeError: greet is not a function
var greet = function() {
  console.log("Hi");
};
```
Yahan sirf variable greet hoist hota hai (as undefined), function body nahi.

| What Gets Hoisted?   | Access Before Declaration    | Notes                          |
| -------------------- | ---------------------------- | ------------------------------ |
| `var`                | ✅ Yes (value is `undefined`) | Avoid using `var` in modern JS |
| `let` / `const`      | ❌ No (TDZ Error)             | Safer, modern way              |
| Function Declaration | ✅ Yes (fully accessible)     | Best for reusable functions    |
| Function Expression  | ❌ No                         | Treated like a `var`           |

