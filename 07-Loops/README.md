

# JavaScript Loops
A loop in JavaScript is used to repeat a block of code multiple times — either for a fixed number of times or until a condition is met.

## Why Use Loops?
Instead of writing the same code again and again, loops let you automate repetition.


### Types of Loops in JavaScript:
| Loop Type    | Description                                      | Common Use Cases                |
| ------------ | ------------------------------------------------ | ------------------------------- |
| `for`        | Runs for a fixed number of times                 | Counting, arrays                |
| `while`      | Runs while a condition is true                   | Unknown repetitions             |
| `do...while` | Runs at least once, then checks the condition    | Menu prompts, retries           |
| `for...of`   | Loops over iterable items like arrays or strings | Arrays, Sets, Strings           |
| `for...in`   | Loops over object keys                           | Objects                         |
| `forEach`    | Calls a function once for each array element     | Array iteration with a callback |



### 1. for Loop
```bash
for (let i = 1; i <= 5; i++) {
  console.log("Number:", i);
}


output:
Number: 1
Number: 2
Number: 3
Number: 4
Number: 5

```

### 2. while Loop
Jab tak condition true ho, tab tak code bar bar chalta rehta hai.
```bash
let i = 0;
while (i < 5) {
  console.log(i);
  i++;
}
```
Jab repeat karne ki exact count nahi pata ho — jaise user input milne tak wait karna.

### 3. do...while Loop
Code kam se kam ek baar chalta hai, phir condition check hoti hai.
```bash
let i = 0;
do {
  console.log(i);
  i++;
} while (i < 5);

```
Menu dikhana, repeat prompt jab tak valid input na mile.

### 4. for...of Loop
Kisi iterable (jaise array, string, set) ke elements ko ek ek karke access karta hai.
```bash
let colors = ['red', 'blue', 'green'];
for (let color of colors) {
  console.log(color);
}

```
Arrays, Strings, Sets — jisme value chahiye har round me.

### 5. for...in Loop
Kisi object ke keys (property names) ko loop karta hai.
```bash
let person = { name: 'Ali', age: 25 };
for (let key in person) {
  console.log(key + ": " + person[key]);
}

```
Objects ke andar ki properties ko access karna.


### 6. forEach
```bash
const numbers = [1, 2, 3];
numbers.forEach(function(num) {
  console.log(num);
});

```


### JavaScript Iterables
Iterables JavaScript mein woh values hoti hain jin par aap for...of loop chala sakte ho. Ye ek special type ke object hote hain jo elements ka sequence provide karte hain — jaise arrays, strings, maps, sets, etc.

