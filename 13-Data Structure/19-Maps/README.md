

# JavaScript Maps – Explained with Examples
A Map in JavaScript is a collection of key-value pairs, similar to an object — but with more flexibility.

### 1. Create a Map
```bash
const myMap = new Map();

myMap.set("name", "John");
myMap.set("age", 25);

console.log(myMap); // Map(2) {'name' => 'John', 'age' => 25}


```

| Feature   | `Map`                           | `Object`                      |
| --------- | ------------------------------- | ----------------------------- |
| Key types | Any (string, object, number)    | Strings or Symbols only       |
| Ordered?  | ✅ Yes                           | ❌ No guarantee                |
| Size      | `map.size`                      | Use `Object.keys(obj).length` |
| Iteration | Easy with `for...of`, `forEach` | Harder                        |


| Method            | Description                    | Example                     |
| ----------------- | ------------------------------ | --------------------------- |
| `set(key, value)` | Add or update a key-value pair | `map.set('color', 'red')`   |
| `get(key)`        | Get the value for a key        | `map.get('color') // 'red'` |
| `has(key)`        | Check if key exists            | `map.has('color') // true`  |
| `delete(key)`     | Remove a key-value pair        | `map.delete('color')`       |
| `clear()`         | Remove all key-value pairs     | `map.clear()`               |
| `size`            | Number of items in map         | `map.size`                  |


### 2. Looping Through a Map
```bash
const map = new Map([
  ["name", "Ali"],
  ["age", 30],
  ["city", "Lahore"]
]);

for (let [key, value] of map) {
  console.log(key, value);
}

```

### 3. forEach() with Map
```bash
map.forEach((value, key) => {
  console.log(`${key} => ${value}`);
});
```

### 4. Map with Any Key Type
```bash
const objKey = { id: 1 };
const map = new Map();

map.set(objKey, "Object as key");
map.set(123, "Number key");
map.set(true, "Boolean key");

console.log(map.get(objKey)); // "Object as key"

```

### 5. Convert Map to Array
```bash
const myMap = new Map([
  ["x", 1],
  ["y", 2]
]);

const arr = Array.from(myMap);
console.log(arr); // [['x', 1], ['y', 2]]
```

### Convert Object to Map
```bash
const obj = { a: 1, b: 2 };
const map = new Map(Object.entries(obj));
```

### Convert Map to Object
```bash
const map = new Map([["a", 1], ["b", 2]]);
const obj = Object.fromEntries(map);
```
