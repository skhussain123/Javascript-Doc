

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



