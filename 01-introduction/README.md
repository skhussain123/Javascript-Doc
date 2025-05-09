

# Introduction to JavaScript





### Why JavaScript is known as a lightweight programming language ?
JavaScript is considered a lightweight language due to its low CPU usage, minimalist syntax, and ease of implementation. With no explicit data types and a syntax similar to C++ and Java, it’s easy to learn and runs efficiently in browsers. Unlike heavier languages like Dart or Java, JavaScript, especially with Node.js, performs faster and uses fewer resources. While it has fewer built-in libraries, this makes it more flexible, though external libraries are often needed for advanced functionality. JavaScript’s efficiency and simplicity make it a top choice for web development.


```bash
<html>
<head></head>
<body>
    <h1>Check the console for the message!</h1>
    <script>
        // This is our first JavaScript program
        console.log("Hello, World!");
    </script>
</body>
</html>
```


### Why JavaScript is known as a lightweight programming language ?
JavaScript is considered a lightweight language due to its low CPU usage, minimalist syntax, and ease of implementation. With no explicit data types and a syntax similar to C++ and Java, it’s easy to learn and runs efficiently in browsers. Unlike heavier languages like Dart or Java, JavaScript, especially with Node.js, performs faster and uses fewer resources. While it has fewer built-in libraries, this makes it more flexible, though external libraries are often needed for advanced functionality. JavaScript’s efficiency and simplicity make it a top choice for web development.

Is JavaScript Compiled or Interpreted or both ?
JavaScript is both compiled and interpreted. The V8 engine improves performance by first interpreting code and then compiling frequently used functions for speed. This makes JavaScript efficient for modern web apps. It’s mainly used for web development but also works in other environments. You can learn it through tutorials and examples.

Just-In-Time (JIT) compilation is a technique used by JavaScript engines (like V8) to improve performance. Here’s how it works

Interpretation: Initially, the code is interpreted line-by-line by the engine.
Hot Code Detection: The engine identifies frequently executed code, such as often-called functions.
Compilation: The “hot” code is compiled into optimized machine code for faster execution.
Execution: The compiled machine code is then executed directly, improving performance compared to repeated interpretation.
JIT compilation balances between interpretation (for quick startup) and compilation (for faster execution).


## JavaScript Versions

Let's take a look at the different versions of ECMAScript, their release years, and the key features they introduced.

| Version | Name             | Release Year | Features |
|---------|------------------|--------------|----------|
| ES1     | ECMAScript 1     | 1997         | Initial Release |
| ES2     | ECMAScript 2     | 1998         | Minor Editorial Changes |
| ES3     | ECMAScript 3     | 1999         | Added:<br>- Regular Expressions<br>- try/catch<br>- Exception Handling<br>- switch case and do-while |
| ES4     | ECMAScript 4     | —            | Abandoned due to conflicts |
| ES5     | ECMAScript 5     | 2009         | Added:<br>- JavaScript "strict mode"<br>- JSON support<br>- JS getters and setters |
| ES6     | ECMAScript 2015  | 2015         | Added:<br>- let and const<br>- Class declaration<br>- import and export<br>- for..of loop<br>- Arrow functions |
| ES7     | ECMAScript 2016  | 2016         | Added:<br>- Block scope for variables<br>- async/await<br>- Array.includes function<br>- Exponentiation Operator |
| ES8     | ECMAScript 2017  | 2017         | Added:<br>- Object.values<br>- Object.entries<br>- Object.getOwnPropertyDescriptors |
| ES9     | ECMAScript 2018  | 2018         | Added:<br>- Spread operator<br>- Rest parameters |
| ES10    | ECMAScript 2019  | 2019         | Added:<br>- Array.flat()<br>- Array.flatMap()<br>- Array.sort is now stable |
| ES11    | ECMAScript 2020  | 2020         | Added:<br>- BigInt primitive type<br>- Nullish coalescing operator |
| ES12    | ECMAScript 2021  | 2021         | Added:<br>- String.replaceAll() Method<br>- Promise.any() Method |
| ES13    | ECMAScript 2022  | 2022         | Added:<br>- Top-level await<br>- New class elements<br>- Static block inside classes |
| ES14    | ECMAScript 2023  | 2023         | Added:<br>- toSorted method<br>- toReversed method<br>- findLast, and findLastIndex methods on Array.prototype and TypedArray.prototype |



