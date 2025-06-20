

# JavaScript Sets – Explained with Examples
A Set in JavaScript is a collection of unique values — that means no duplicates are allowed.

### 1. Create a Set
```bash
const mySet = new Set();
mySet.add(1);
mySet.add(2);
mySet.add(2); // Duplicate – ignored
console.log(mySet); // Set(2) {1, 2}

```

| Method          | Description            | Example                                |
| --------------- | ---------------------- | -------------------------------------- |
| `add(value)`    | Add value to Set       | `set.add(5)`                           |
| `delete(value)` | Remove a value         | `set.delete(2)`                        |
| `has(value)`    | Check if value exists  | `set.has(1)` → `true`                  |
| `clear()`       | Remove all values      | `set.clear()`                          |
| `size`          | Get total unique items | `set.size`                             |
| `forEach()`     | Loop through set       | `set.forEach(val => console.log(val))` |

### 2. Loop Through a Set
```bash
const fruits = new Set(["apple", "banana", "mango"]);

for (let fruit of fruits) {
  console.log(fruit);
}
```

### 3. Convert Set to Array
```bash
const set = new Set([1, 2, 3]);
const arr = [...set];
console.log(arr); // [1, 2, 3]
```

| Feature         | Set                        | Array               |
| --------------- | -------------------------- | ------------------- |
| Duplicates      | ❌ Not allowed              | ✅ Allowed           |
| Order           | Insertion order            | Insertion order     |
| Access by index | ❌ No (`set[0]` won't work) | ✅ Yes               |
| Use case        | Unique values, fast lookup | Lists, ordered data |

