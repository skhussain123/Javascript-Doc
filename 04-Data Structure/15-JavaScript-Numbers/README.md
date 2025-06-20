


# JavaScript Numbers
JavaScript numbers are primitive data types, and unlike other programming languages, you don’t need to declare different numeric types like int, float, etc. JavaScript numbers are always stored in double-precision 64-bit binary format IEEE 754. This format stores numbers in 64 bits:

* 0-51 bits store the value (fraction)
* 52-62 bits store the exponent
* 63rd bit stores the sign


## Numeric Types in JavaScript
In JavaScript, numbers play an important role, and understanding their behavior is essential for effective programming. Let’s explore the various aspects of numeric types in JavaScript.

### 1. The Only Numeric Type
As we know, JavaScript has only one numeric type: the double-precision 64-bit binary format IEEE 754, which means that it doesn’t differentiate between integers and floating-point numbers explicitly. Instead, it uses a unified approach for all numeric values.

* Integers and floating-point numbers are both represented using this format.
* The numeric precision is 53 bits, allowing for an accurate representation of integer values ranging from -2^53 + 1 to 2^53 – 1.


2. Scientific Notation
JavaScript allows writing extra-large or extra-small numbers using scientific (exponent) notation.
```bash
let a  =  156e5;
let b =   156e-5;
console.log(a);
console.log(b);

output:
15600000
0.00156
```

### 3. Integer Precision
Integers (numbers without a period or exponent notation) are accurate up to 15 digits.
```bash
let a = 999999999999999;
let b = 9999999999999999;
console.log(a);
console.log(b);

output:
999999999999999
10000000000000000
```

### 4. Floating Point Precision
Floating point arithmetic is not always 100% accurate due to binary representation limitations.

```bash
let x = 0.22 + 0.12;   //x will be 0.33999999999999997
```
**To solve this problem, multiply and divide:**
```bash
let x = (0.22 * 10 + 0.12 * 10) / 10;    // x will be 0.34
```

```bash
let x = 0.22 + 0.12;
let y = (0.22 * 10 + 0.12 * 10) / 10;
console.log(x);
console.log(y);

output:
0.33999999999999997
0.34
```

### 5. Adding Numbers and Strings
JavaScript uses the `+` operator for both addition and concatenation.
Numbers are added, when strings are concatenated.
```bash
// Adding two numbers
let x = 10;
let y = 15;
let z = x + y;
console.log(z);

// Concatenating two strings:

let a = "10";
let b = "30";
let c  = a + b;
console.log(c);

output:
25
1030

```

### 6. Numeric Strings
JavaScript automatically converts the numeric strings to numbers in most operations like.
```bash
let x  = "100" / "10";
let y  = "100" * "10";
let z = "100" - "10";
console.log(x);
console.log(y);
console.log(z);

output:
10
1000
90

```


# Number Literals
The types of number literals You can use decimal, binary, octal, and hexadecimal.

### 1. Decimal Numbers
JavaScript Numbers does not have different types of numbers(ex: int, float, long, short) which other programming languages do. It has only one type of number and it can hold both with or without decimal values.
```bash
let a=33;
let b=3.3;
console.log(a);
console.log(b);

output:
33
3.3
```

### 2. Octal Number
If the number starts with 0 and the following digits are smaller than 8. It will be parsed as an Octal Number. 
```bash
let x = 0562;
console.log(x);

output:
370
```

### 3. Binary Numbers
They start with 0b or 0B followed by 0’s and 1’s. 
```bash
let x = 0b11; 
let y = 0B0111;

console.log(x);
console.log(y);

output:
3
7

```

### 4. Hexadecimal Numbers
They start with 0x or 0X followed by any digit belonging (0123456789ABCDEF) 
```bash
let x = 0xfff;
console.log(x);

output:
4095
```

# Number Coercion in JavaScript
In JavaScript, coercion refers to the automatic or implicit conversion of values from one data type to another. When different types of operators are applied to values, JavaScript performs type coercion to ensure that the operation can proceed. Let’s explore some common examples of coercion:

### 1. Undefined to NaN
When you perform an operation involving undefined, JavaScript returns NaN (Not-a-Number).
```bash
const res = undefined + 10;
console.log(res); // NaN

output:
NaN
```

### 2. Null to 0
The value null is coerced to 0 when used in arithmetic operations.
```bash
const total = null + 5;
console.log(total); // 5

output:
5
```

### 3. Boolean to Number
Boolean values (true and false) are converted to numbers: 1 for true and 0 for false.
```bash
const n1 = true + 10;
const n2 = false + 10;

console.log(n1);
console.log(n2);

output:
11
10
```

### 4. String to Number
When performing arithmetic operations, JavaScript converts strings to numbers. If the string cannot be parsed as a valid number, it returns NaN.
```bash
const s1 = '42';
const s2 = 'hello';

const strToNum1 = Number(s1);
const strToNum2 = Number(s2);

console.log(strToNum1);
console.log(strToNum2);

output:
42
NaN
```

### 5. BigInts and Symbols
Attempting to coerce Symbol values to numbers results in a TypeError.
```bash
const symbol = Symbol('mySymbol');

const symToNum = Number(symbol); // TypeError
console.log(symToNum);

output:
TypeError: Cannot convert a Symbol value to a number
```

## JavaScript Number Methods
Now, we will use Number methods such as toString(), toExponential(), toPrecision(), isInteger(), and toLocaleString() method. Let’s see the examples of these Number methods.
```bash
let x = 21
console.log(x.toString());
console.log(x.toExponential());
console.log(x.toPrecision(4));
console.log(Number.isInteger(x));
console.log(x.toLocaleString("bn-BD"));

output:
21
2.1e+1
21.00
true
২১

```