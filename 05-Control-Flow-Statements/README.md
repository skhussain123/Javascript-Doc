



# **JavaScript- Control Flow Statements**
Control flow statements in JavaScript control the order in which code is executed. These statements allow you to make decisions, repeat tasks, and jump between parts of a program based on specific conditions.

## **1. Decision-Making Statements**

### **JavaScript if Statement**
The if statement executes a block of code only if a specified condition is true.
```bash
const age = 18;
if (age >= 18) {
    console.log("You are an adult.");
}

outout:
You are an adult.
```

* Checks if age is greater than or equal to 18.
* Logs "You are an adult." if the condition is true.

### **JavaScript if...else Statement**
The if...else statement provides an alternate block of code to execute if the condition is false.
```bash
const score = 40;
if (score >= 50) {
    console.log("You passed.");
} else {
    console.log("You failed.");
}
output:
You failed.
```

* It will log "You passed." if the score is 50 or more.
* Otherwise, logs "You failed."


### **JavaScript if...else if...else Statement**
The if...else if...else statement is used when you want to handle multiple conditions.
```bash
const temp = 25;
if (temp > 30) {
    console.log("It's hot.");
} else if (temp >= 20) {
    console.log("It's warm.");
} else {
    console.log("It's cold.");
}

output:
It's warm.
```

* Checks if the temperature is greater than 30, logs "It's hot."
* If not, checks if it's between 20 and 30, logs "It's warm."
* Otherwise, logs "It's cold."


## **2. Loops**
### **JavaScript for loop**
The for loop continuously execute a block of code to a set number of times.
```bash
for (let i = 1; i <= 5; i++) {
    console.log(i);
}
output:
1
2
3
4
5
```

* Initializes i with 1 and checks if i <= 5.
* Executes the console.log statement and increments i by 1 in each iteration.
* Stops the loop when i exceeds 5.

### **JavaScript while loop**
The while loop repeats a block of code as long as the condition is true.
```bash
let i = 1;
while (i <= 5) {
    console.log(i);
    i++;
}

output:
1
2
3
4
5
```
* Starts with i = 1 and checks if i <= 5.
* Logs the value of i and increments it by 1 after each iteration.
* Stops the loop when i exceeds 5.

### **JavaScript do...while loop**
The do...while loop executes the block of code at least once before checking the condition.
```bash
let i = 1;
do {
    console.log(i);
    i++;
} while (i <= 5);

output:
1
2
3
4
5
```

* Executes the console.log statement once, even if the condition is false.
* Continues looping until the condition i <= 5 is no longer true.


## **3. Branching Statements**
### **JavaScript return Statement**
The return statement is used to end the execution of a function and optionally return a value to the function caller.
```bash
function add(a, b) {
    return a + b;
}
const res = add(5, 3);
console.log(res);

output:
8
```

* return n1 + n2 ends the function and sends the sum of a and b back to the caller.
* The returned value is stored in the result.


### **JavaScript break Statement**
The break statement is used to exit a loop or switch statement prematurely.
```bash
for (let i = 1; i <= 5; i++) {
    if (i === 3) break;
    console.log(i);
}

output:
1
2
```
* It will log 1 and 2 to the console.
* Exits the loop when i equals 3.


### **JavaScript continue Statement**
The continue statement skips the current iteration of a loop and proceeds to the next one.
```bash
for (let i = 1; i <= 5; i++) {
    if (i === 3) continue;
    console.log(i);
}
output:
1
2
4
5
```
* It will skip logging when i equals 3.
* Logs 1, 2, 4, and 5 to the console.


## **4. Switching Statements**
### **JavaScript switch Statement**
The switch statement evaluates an expression and executes a block of code based on matching cases. It provides an alternative to long if-else chain.
```bash
const day = "Monday";
switch (day) {
    case "Monday":
        console.log("Start of the week.");
        break;
    case "Friday":
        console.log("End of the workweek.");
        break;
    default:
        console.log("It's a regular day.");
}
output:
Start of the week.
```
* Checks the value of day and matches it to a case.
* Logs "Start of the week." if day is "Monday".
* Logs "End of the workweek." if day is "Friday".
* Logs "It's a regular day." if no cases match.


## **Uses of Control Flow Statements**
Control flow statements are backbone in programming for

* Decision-Making: To execute specific blocks of code based on conditions (e.g., if, if...else).
* Branching: To exit loops or skip iterations (break, continue).
* Looping: To repeat tasks (for, while, do...while).
* Switching: To handle multiple conditions effectively (switch).



