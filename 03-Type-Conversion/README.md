# **Type Conversion and Type Coercion in JavaScript**
Data types in JavaScript are flexible due to which the type of the variables can be changed when the program runs. Type Conversion and Type Coercion are the two ways through which we can change the data type of the variables from one type to the other.

**Type Conversion**
Type Conversion is the process in JavaScript in which the data type of the variables is converted from one type to another type manually. This is also known as explicit type casting.

* Performed manually by the programmer.
* Uses built-in JavaScript methods like Number(), String(), and Boolean().
* Ensures control over data types in code.

## **Performing type conversion-**


### **1. String to Number**
We can convert a string into numbers using the Number() function, parseInt(), and parseFloat() methods
```bash
let s = "123";
let n = Number(s);  // Converts string to number
console.log(n);

output:
123
```

### **2. Number to String**
We can convert a number into a string using String() function or we can concate it with an empty string("").
```bash
let n = 123;
let s = String(n);  //Converts number to string
console.log(s);

output:
123
```

### **3. Boolean to Number**
We can convert a boolean into a number using Number(), so true becomes 1 and false becomes 0.
```bash
let bool = true;
let n = Number(bool);  //Converts boolean to number
console.log(n);

output:
1
```


### **4. Boolean to String**
We can convert boolean into string using String() or by contacting it with empty string.
```bash
let bool = true;
let s = String(bool);  //Converts boolean to string
console.log(s);

output:
true
```


## **Type Coercion**
Type coercion is the automatic conversion of one data type to another by JavaScript during operations. This is also known as implicit type casting.

* Performed automatically by JavaScript.
* Happens mostly in comparison and arithmetic operations.
* Can lead to unexpected results if not handled properly.

### **1. String + Number**
JavaScript will automatically or implicitly convert the number to a string if there is the string present in the arithmetic operation.
```bash
let n = 5;
let s = "5";
let res = n + s;  // JavaScript converts num to string
console.log(res); 
console.log(typeof(res))

output:
55
string
```

### **2. Boolean + Number**
JavaScript converts the boolean value into a number, true becomes 1 and false becomes 0, when we perform the arithematic operations.
```bash
let bool = true;
let n = 10;
let res = bool + n;  // JavaScript converts boolean to number
console.log(res);

output:
11
```

### **3. Comparison of Different Types**
JavaScript convert the two value of data type into the common type when we compare there values.
```bash
let s = "10";
let n = 10;
console.log(s == n);  // true, JavaScript converts str to number

output:
true

```

### **4. Boolean Context**
Javascript converts non-boolean value into the boolean value when the value is in the if statement.
```bash
let s = "";
if (s) {
    console.log("This won't print");  // Empty string is falsy
} else {
    console.log("This will print");  // Empty string is coerced to false
}

```


## **Difference Between Type Conversion and Type Coercion**

| Feature     | Type Conversion (Explicit) | Type Coercion (Implicit) |
|-------------|----------------------------|--------------------------|
| **Performed by** | Programmer | JavaScript Engine |
| **Type**    | Explicit | Implicit |
| **Control** | Full control | Happens automatically |
| **Examples** | `Number("5")` → `5` | `"5" - 2` → `3` |



