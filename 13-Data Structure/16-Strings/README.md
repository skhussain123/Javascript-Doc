

# String in DSA Using JavaScript
A string in JavaScript is a sequence of characters enclosed in single (‘), double (“), or backticks (`). Strings in JavaScript are immutable, meaning their contents cannot be changed after creation. Any operation that modifies a string actually creates a new string.

```bash
let s = "GfG";
console.log(s[0]);
console.log(s.length);

output:
G
3

```

## JavaScript String Methods
JavaScript strings are the sequence of characters. They are treated as Primitive data types. In JavaScript, strings are automatically converted to string objects when using string methods on them. This process is called auto-boxing. The following are methods that we can call on strings.

* slice() extracts a part of the string based on the given starting-index and ending-index and returns a new string.
substring() returns the part of the given string from the start index to the end index. Please see String.slice and String.substring for details.
* substr() This method returns the specified number of characters from the specified index from the given string. It extracts a part of the original string.
* replace() replaces a part of the given string with another string or a regular expression. The original string will remain unchanged.
* replaceAll() returns a new string after replacing all the matches of a string with a specified string or a regular expression. The original string is left unchanged after this operation.
* toUpperCase() converts all the characters present in the String to upper case and returns a new String with all characters in upper case. This method accepts a single parameter stringVariable string that you want to convert in upper case.
* toLowerCase() converts all the characters present in the so lowercase and returns a new string with all the characters in lowercase.
* trim() is used to remove either white spaces from the given string. This method returns a new string with removed white spaces. This method is called on a String object. This method doesn’t accept any parameter.
* trimStart() removes whitespace from the beginning of a string. The value of the string is not modified in any manner, including any whitespace present after the string.
* trimEnd() removes white space from the end of a string. The value of the string is not modified in any manner, including any white-space present before the string.
* padStart() pad a string with another string until it reaches the given length. The padding is applied from the left end of the string.
* padEnd() pad a string with another string until it reaches the given length. The padding is applied from the right end of the string.
* charAt() returns the character at the specified index.
* charCodeAt() returns a number that represents the Unicode value of the character at the specified index. This method accepts one argument.
* split() splits the string into an array of sub-strings. This method returns an array. This method accepts a single parameter character on which you want to split the string.


## Most Common Methods
### 1. slice()
slice() extracts a part of the string based on the given stating-index and ending-index and returns a new string.
```bash
// Define a string variable 
let A = 'Geeks for Geeks';

// Use the slice() method to extract a substring
let b = A.slice(0, 5);
let c = A.slice(6, 9);
let d = A.slice(10);

// Output the value of variable
console.log(b);
console.log(c);
console.log(d);

output:
Geeks
for
Geeks

```

### 2. substring()
substring() returns the part of the given string from the start index to the end index. Indexing starts from zero (0).
```bash
// Define a string variable
let str = "Mind, Power, Soul";

// Use the substring() method to extract a substring 
let part = str.substring(6, 11);

// Output the value of variable
console.log(part);

output:
Power

```

### 3. substr()
substr() This method returns the specified number of characters from the specified index from the given string. It extracts a part of the original string.
```bash
// Define a string variable 'str'
let str = "Mind, Power, Soul";

// Use the substr() method to extract a substring f
let part = str.substr(6, 5);

// Output the value of variable
console.log(part);

output:
Power
```

### 4. replace()
replace() replaces a part of the given string with another string or a regular expression. The original string will remain unchanged.
```bash
// Define a string variable 'str' 
let str = "Mind, Power, Soul";

// Use the replace() method to replace the substring
let part = str.replace("Power", "Space");

// Output the resulting string after replacement
console.log(part);

output:
Mind, Space, Soul

```

### 5. replaceAll()
replaceAll() returns a new string after replacing all the matches of a string with a specified string or a regular expression. The original string is left unchanged after this operation.
```bash
// Define a string variable 'str'
let str = "Mind, Power, Power, Soul";

// Use the replaceAll() method to replace all occurrences
//of "Power" with "Space" in the string 'str'
let part = str.replaceAll("Power", "Space");

// Output the resulting string after replacement
console.log(part);

output:
Mind, Space, Space, Soul

```

### 6. toUpperCase()
toUpperCase() converts all the characters present in the String to upper case and returns a new String with all characters in upper case. This method accepts single parameter stringVariable string that you want to convert in upper case.
```bash
// Define a string variable
let gfg = 'GFG ';

// Define another string variable 
let geeks = 'stands-for-GeeksforGeeks';

// Convert the string 'geeks' to uppercase using the toUpperCase() method
console.log(geeks.toUpperCase());

output:
STANDS-FOR-GEEKSFORGEEKS

```

### 7. toLowerCase()
toLowerCase() converts all the characters present in the so lowercase and returns a new string with all the characters in lowercase.
```bash
// Define a string variable
let gfg = 'GFG ';

// Define a string variable 
let geeks = 'stands-for-GeeksforGeeks';

// Convert the string 'geeks' to lowercase using the toLowerCase() method
console.log(geeks.toLowerCase());

output:
stands-for-geeksforgeeks

```

### 8. concat()
concat() combines the text of two strings and returns a new combined or joined string. To concatenate two strings, we use the concat() method on one object of string and send another object of string as a parameter. This method accepts one argument. The variable contains text in double quotes or single quotes.
```bash
let gfg = 'GFG ';
let geeks = 'stands for GeeksforGeeks';

// Accessing concat method on an object
// of String passing another object 
// as a parameter
console.log(gfg.concat(geeks));

output:
GFG stands for GeeksforGeeks

```

### 9.trim()
trim() is used to remove either white spaces from the given string. This method returns a new string with removed white spaces. This method is called on a String object. This method doesn’t accept any parameter.
```bash
let gfg = 'GFG    ';
let geeks = 'stands-for-GeeksforGeeks';

// Storing new object of string
// with removed white spaces
let newGfg = gfg.trim();

// Old length
console.log(gfg.length);

// New length
console.log(newGfg.length)

output:
7
3
```

### 10. trimStart()
trimStart() removes whitespace from the beginning of a string. The value of the string is not modified in any manner, including any whitespace present after the string.
```bash
// Define a string variable 
let str = "  Soul";

// Output the original value of the string 
console.log(str);

// Use the trimStart() method to remove leading whitespace from the string 'str'
let part = str.trimStart();

// Output the resulting string after removing leading whitespace
console.log(part);

output:
Soul
Soul

```

### 11. trimEnd()
trimEnd() removes white space from the end of a string. The value of the string is not modified in any manner, including any white-space present before the string.
```bash
// Define a string variable 
let str = "Soul  ";

// Output the original value of the string 'str'
console.log(str);

// Use the trimEnd() method to remove trailing whitespace from the string 'str'
let part = str.trimEnd();

// Output the resulting string after removing trailing whitespace
console.log(part);

output:
Soul  
Soul
```

### 12. padStart()
padStart() pad a string with another string until it reaches the given length. The padding is applied from the left end of the string.
```bash
// Define a string variable 
let stone = "Soul";

// Use the padStart() method to add padding characters "Mind "
//to the beginning of the string 'stone' 
stone = stone.padStart(9, "Mind ");

// Output the resulting string after padding
console.log(stone);

output:
Mind Soul
```

### 13. padEnd()
padEnd() pad a string with another string until it reaches the given length. The padding is applied from the right end of the string.
```bash
// Define a string variable 
let stone = "Soul";

// Use the padEnd() method to add padding characters
//" Power" to the end of the string 'stone' 
stone = stone.padEnd(10, " Power");

// Output the resulting string after padding
console.log(stone);

output:
Soul Power

```

### 14. charAt()
charAt() returns the character at the specified index. String in JavaScript has zero-based indexing.
```bash
let gfg = 'GeeksforGeeks';
let geeks = 'GfG is the best platform to learn and\n'+
'experience Computer Science.';

// Print the string as it is
console.log(gfg); 

console.log(geeks); 

// As string index starts from zero
// It will return first character of string
console.log(gfg.charAt(0)); 

console.log(geeks.charAt(5));

output:
GeeksforGeeks
GfG is the best platform to learn and
experience Computer Science.
G
s

```

### 15. charCodeAt()
charCodeAt() returns a number that represents the Unicode value of the character at the specified index. This method accepts one argument.
```bash
let gfg = 'GeeksforGeeks';
let geeks = 'GfG is the best platform\n\
to learn and experience\n\
Computer Science.';

// Return a number indicating Unicode
// value of character at index 0 ('G')
console.log(gfg.charCodeAt(0));
console.log(geeks.charCodeAt(5));

output:
71
115


```

### 16. split()
split() splits the string into an array of sub-strings. This method returns an array. This method accepts a single parameter character on which you want to split the string.
```bash
let gfg = 'GFG '
let geeks = 'stands-for-GeeksforGeeks'

// Split string on '-'. 
console.log(geeks.split('-'))

output:
[ 'stands', 'for', 'GeeksforGeeks' ]

```


## JavaScript String Search
### JavaScript String indexOf()
The indexOf() method returns the index (position) of the first occurrence of a string in a string, or it returns -1 if the string is not found:
```bash
let text = "Please locate where 'locate' occurs!";
let index = text.indexOf("locate");

output:
7
```

### JavaScript String lastIndexOf()
The lastIndexOf() method returns the index of the last occurrence of a specified text in a string:
```bash
let text = "Please locate where 'locate' occurs!";
let index = text.lastIndexOf("locate");

output:
21
```

**Both indexOf(), and lastIndexOf() return -1 if the text is not found:**
```bash
let text = "Please locate where 'locate' occurs!";
let index = text.lastIndexOf("John");

output:
-1
```

Both methods accept a second parameter as the starting position for the search:
```bash
let text = "Please locate where 'locate' occurs!";
let index = text.indexOf("locate", 15);

output:
21

```

The lastIndexOf() methods searches backwards (from the end to the beginning), meaning: if the second parameter is 15, the search starts at position 15, and searches to the beginning of the string.
```bash
let text = "Please locate where 'locate' occurs!";
text.lastIndexOf("locate", 15);

output:
7

```

### JavaScript String search()
The search() method searches a string for a string (or a regular expression) and returns the position of the match:
```bash
let text = "Please locate where 'locate' occurs!";
text.search("locate");

output:
7

```

```bash
let text = "Please locate where 'locate' occurs!";
text.search(/locate/);

output:
7

```

The two methods are NOT equal. These are the differences:

* The search() method cannot take a second start position argument.
* The indexOf() method cannot take powerful search values (regular expressions).


### JavaScript String match()
The match() method returns an array containing the results of matching a string against a string (or a regular expression).
```bash
let text = "The rain in SPAIN stays mainly in the plain";
text.match("ain");

output:
1 ain

```

```bash
let text = "The rain in SPAIN stays mainly in the plain";
text.match(/ain/);

output:
1 ain

```

```bash
let text = "The rain in SPAIN stays mainly in the plain";
text.match(/ain/g);

output:
3 ain,ain,ain

```

```bash
let text = "The rain in SPAIN stays mainly in the plain";
text.match(/ain/gi);

output:
4 ain,AIN,ain,ain

```

### JavaScript String matchAll()
The matchAll() method returns an iterator containing the results of matching a string against a string (or a regular expression).

```bash
let text = "I love cats. Cats are very easy to love. Cats are very popular."
const iterator = text.matchAll("Cats");

output:
Cats,Cats
```


```bash
const iterator = text.matchAll(/Cats/gi);

output:
cats,Cats,Cats
```

### JavaScript String includes()
The includes() method returns true if a string contains a specified value.

Otherwise it returns false.
```bash
let text = "Hello world, welcome to the universe.";
text.includes("world");

output:
true
```

```bash
let text = "Hello world, welcome to the universe.";
text.includes("world", 12);

output:
false
```

### JavaScript String startsWith()
The startsWith() method returns true if a string begins with a specified value.

Otherwise it returns false:

```bash
let text = "Hello world, welcome to the universe.";
text.startsWith("Hello");

output:
true
```

```bash
let text = "Hello world, welcome to the universe.";
text.startsWith("world")

output:
false

```

```bash
let text = "Hello world, welcome to the universe.";
text.startsWith("world", 5)

output:
false
```

```bash
let text = "Hello world, welcome to the universe.";
text.startsWith("world", 6)

output:
true
```

## JavaScript String endsWith()
The endsWith() method returns true if a string ends with a specified value.

Otherwise it returns false:
```bash
let text = "John Doe";
text.endsWith("Doe");

output:
true
```

```bash
let text = "Hello world, welcome to the universe.";
text.endsWith("world", 11);

output:
true
```