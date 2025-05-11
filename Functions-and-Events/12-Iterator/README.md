



# JavaScript Iterator
Iterator JavaScript ka ek tareeqa hai step-by-step kisi collection (array, string, etc.) ko read karne ka.

Iterator ek object hota hai jo .next() method provide karta hai, jo next value deta hai — jab tak items khatam na ho jayein.


```bash
const array = [10, 20, 30];
const iterator = array[Symbol.iterator]();

console.log(iterator.next()); // { value: 10, done: false }
console.log(iterator.next()); // { value: 20, done: false }
console.log(iterator.next()); // { value: 30, done: false }
console.log(iterator.next()); // { value: undefined, done: true }

```

### Important Properties of an Iterator:
* .next() → ek object return karta hai:
  * value: current item
  * done: false jab tak aur values bachi hoon, true jab end ho jaye


## Real-Life Use: for...of loop (uses iterator under the hood)
```bash
const colors = ['red', 'blue', 'green'];

for (let color of colors) {
  console.log(color);
}

```
Ye for...of loop internally iterator hi use karta hai.


## Custom Iterator
```bash
function customIterator(items) {
  let index = 0;
  return {
    next: function() {
      return index < items.length
        ? { value: items[index++], done: false }
        : { value: undefined, done: true };
    }
  };
}

const iter = customIterator(['a', 'b', 'c']);
console.log(iter.next()); // { value: 'a', done: false }

```
* Iterator allows step-by-step access to elements.
* Used in loops (for...of) and when dealing with custom data streams.
* Useful for efficient memory handling (e.g., large datasets or generators).
