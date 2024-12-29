---
type: Programming
title: Namaste JavaScript Ep. 5
description: SHORTEST JS Program 🔥window & this keyword
modificationDate: 2024-12-29 13:50
tags: []
timestamp: '2024-12-27'
resource: null
difficulty: Unraked
---

### Lesson Main Points

Empty file is the shortest JavaScript file

Global Space is for all the code that aren't in a *function*

JavaScript file can be run on different environments (browsers, servers ...) and its Global Object name is different base on the platform on which it is running. 

### Short Notes

Running Empty File in JavaScript -> Global ExeContext Created

- **JavaScript engine also creates Window (see** ***console*** **>> type** ***Window)***

    **Window** is a global object that is created along with the Global ExeContext

    ![Screenshot for the Global Object Creation](./Media/Global%20Object%20Creation.jpeg)

    The created Window is like an object with a lot of functions and variables created by JavaScript and put into the Global ExeContext

- **JavaScript engine also create** ***this*** **keyword**

    Global Level ***this*** is equal to the Global Object (Window for browser)

---

```javascript
var a = 10;
function b () {
  var x = 10;
}
console.log(window.a); //accessing var by mentioning the Global Object name
console.log(a); //accessing var without mentioning anything in the front
console.log(this.a); //on the Global level, this is a keyword for the Global Object 
console.log(x);
```


---

> Output:
​10                            index.js:5
​10                            index.js:6
​10                            index.js:7
​Uncaught ReferenceError: x is not defined at index.js:8


---

Whenever we try to access any var in the program and we don't put anything in front of it, JavaScript Engine assumes that it is in the Global Space/ Object and auto access from there.

In Reference to the Output: x is shown as not defined since it is not in the Global Object but in a function space which is independent.

### Takeaway

Whenever any JavScript Program is run, it creates the following things...

- Global Object (known by different names depending on the running platform| e.g Brower >> Window)

- Global Execution Context

- *this* variable

