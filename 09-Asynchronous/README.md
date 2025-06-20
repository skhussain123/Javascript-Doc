


### 1. Synchronous 
Jab JavaScript ka code line by line chalti hai, pehle wali line complete hoti hai, phir agli chalti hai, usko kehte hain synchronous code.
```bash
console.log("1");
console.log("2");
console.log("3");

```
* Agar koi function zyada waqt le raha ho (jaise file read karna ya server se data lana), to poora program ruk jata hai jab tak wo kaam complete na ho

### 2. Asynchronous Code – (Wait mat karo, agla kaam shuru karo)
Jab koi kaam waqt leta ho, to JavaScript usko chhor kar agla kaam shuru kar leti hai. Jab pehle kaam complete hota hai, to baad me uska result milta hai. Isko kehte hain asynchronous code.

```bash
console.log("1");

setTimeout(function() {
  console.log("2");
}, 2000);

console.log("3");
```
* Pehle 1 aur 3 print hua. setTimeout wala kaam delay ho gaya, to 2 baad me aaya.

### Callback 
Callback ek aisi function hoti hai jo doosre function ko argument me di jaati hai, aur jab wo doosra function apna kaam complete karta hai, tab callback ko call karta hai.

```bash
function greetUser(name, callback) {
  console.log("Hello, " + name);
  callback();
}

function sayBye() {
  console.log("Allah Hafiz!");
}

greetUser("Ahmed", sayBye);
```

### Callback Hell
Jab aap ek function ke andar doosra function call karte ho, phir uske andar teesra, phir uske andar chautha...
is tarah ka code bahut complex aur ganda ho jata hai — usi ko kehte hain Callback Hell.
```bash
loginUser("Ahmed", function(user) {
  getUserProfile(user, function(profile) {
    getUserPosts(profile, function(posts) {
      getComments(posts, function(comments) {
        console.log(comments);
      });
    });
  });
});
```
* Har function ke andar ek aur callback. Yeh structure "pyramid of doom" banata hai — samajhna aur maintain karna mushkil.

#### Callback Hell Ka Solution:
```bash
function getData(dataid, getNextData) {
  setTimeout(() => {
    console.log("data", dataid);
    if (getNextData) {
      getNextData();
    }
  }, 2000);
}

getData(1, () => {
  getData(2, () => {
    getData(3, () => {
      getData(4);
    });
  });
});

```





### Async / Await
async function hota hai jo promise return karta hai, aur await ka matlab hota hai "ruk jao jab tak kaam complete na ho jaye.