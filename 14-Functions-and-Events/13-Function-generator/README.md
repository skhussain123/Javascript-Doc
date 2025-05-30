



# JavaScript Function Generator
Generator Function JavaScript mein ek special function hota hai jo pause aur resume ho sakta hai execution ke dauran.

Ye normal function se alag hota hai:

* Normal function poora ek baar chalta hai
* mGenerator function ruk ruk ke chalta hai using yield

```bash
function* generatorFunction() {
  yield 'First';
  yield 'Second';
  yield 'Third';
}



```
* function* ← star lagta hai to mark it as a generator.
* yield ← returns value aur wahan ruk jaata hai.
* Generator function call karne pe ek iterator object milta hai.


```bash
function* greetGenerator() {
  yield "Hello";
  yield "How are you?";
  yield "Goodbye";
}

const greeter = greetGenerator();

console.log(greeter.next()); // { value: 'Hello', done: false }
console.log(greeter.next()); // { value: 'How are you?', done: false }
console.log(greeter.next()); // { value: 'Goodbye', done: false }
console.log(greeter.next()); // { value: undefined, done: true }

```

### Infinite Number Generator
```bash
function* countForever() {
  let i = 1;
  while (true) {
    yield i++;
  }
}

const counter = countForever();
console.log(counter.next().value); // 1
console.log(counter.next().value); // 2
console.log(counter.next().value); // 3 ...


```

###  Generator vs Normal Function
| Feature           | Normal Function | Generator Function          |
| ----------------- | --------------- | --------------------------- |
| Runs all at once? | ✅ Yes           | ❌ No, stops at each `yield` |
| Pause and resume? | ❌ No            | ✅ Yes                       |
| Returns?          | One value       | Many values (using `yield`) |
| Returns type?     | Any             | Iterator Object             |


## Use Case:
| Use Case             | Why Use Generator?                         |
| -------------------- | ------------------------------------------ |
| Large data streams   | Process data step-by-step, not all at once |
| Asynchronous control | Replace `async/await` or callbacks         |
| Infinite sequences   | Like number generators                     |


* function* → Generator function
* yield → Step-by-step value dena + pause
* .next() → Call to get next value
* Useful for lazy loading, large data, infinite loops, and asynchronous tasks
