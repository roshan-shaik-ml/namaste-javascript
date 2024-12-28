---
type: Programming
title: Namaste JavaScript Ep. 3
description: Hoisting in JavaScript 🔥(variables & functions)
tags: [JavaScript]
timestamp: '2024-12-27'
resource: '[https://www.youtube.com/watch?v=Fnlnw8uY6jo&list=PLlasXeu85E9cQ32gLCvAvr9vNaUccPVNP&index=4](https://www.youtube.com/watch?v=Fnlnw8uY6jo&list=PLlasXeu85E9cQ32gLCvAvr9vNaUccPVNP&index=4)'
difficulty: Unraked
---

### Lesson Main Points

***Hoisting***: Phenomenal in JavaScript by which you can access the variables and functions even before you have initialised it without any error.

***Arrow Function****:* behaves like a variable in JavaScript.

Only a proper formal way of function initialisation will store the whole code in the exeContext.

- **Demo of Call Stack in the Browser**

    [image](images/getNameExeContext.jpg)

    Global ExeContext: (anonymous) currently at line 8 that leads to executing the getName()

    Current function ExeContext at Line 5

    Blue arrow indicates where the current control of the program (currenly at Line 5 for getName function operation)

    [image](images/globalExeContext.jpg)

    Function Execution Context popped out of the stack and the control goes back to the global ExeContext and a following line has started its execution.

### Short Notes

---

Case 1 | Call function and var after initialisation (Common)

```javascript
var x = 7;

function getName() {
  console.log("Namaste JavaScript");
}

getName();
console.log(x);
```


---

> Output: 

Namaste JavaScript

7


---

---

Case 2 | Call the functions and var before the initialisation

```javascript
getName();
console.log(x);

var x = 7;

function getName() {
  console.log("Namaste JavaScript");
}
```


---

> Output: 

Namaste JavaScript

undefined


---

---

Case 3 | Call the function and the var that doesn't exist before the initialisation

```javascript
getName();
console.log(x);

//var x = 7;

function getName() {
  console.log("Namaste JavaScript");
}
```


---

> Output: 

Namaste JavaScript

Uncaught RefereneceError: x is not defined at index.js:2


---

---

Case 4 | Console output for the function itself after initialisation

```javascript
//getName();
//console.log(x);

var x = 7; 

function getName() {
  console.log("Namaste JavaScript");
}

console.log(getName);
```


---

> Output: 

*f getName() {
console.log("Namaste JavaScript");
}*


---

---

Case 5 | Console output for the function itself before initialisation

```javascript
//getName();
//console.log(x);
console.log(getName);

var x = 7; 

function getName() {
  console.log("Namaste JavaScript");
}
```


---

> Output: 

*f getName() {
console.log("Namaste JavaScript");
}*


---

---

Case 6 | Calling function, var and function code before initialisation

```javascript
getName();
console.log(x);
console.log(getName);

var x = 7; 

function getName() {
  console.log("Namaste JavaScript");
}
```


---

> Output: 

Namaste JavaScript

undefined

*f getName() {
console.log("Namaste JavaScript");
}*


---

---

Case 7 | Call the **Arrow function** before initialisation

```javascript
getName();
console.log(x);
console.log(getName);

var x = 7; 

var getName = () => {
  console.log("Namaste JavaScript");
}

//another way of writing a function but this will still count getName2 as var
var getName2 = function () {
    console.log("Namaste JavaScript");
}
```


---

> Output: 

Uncaught RefereneceError: x is not defined at index.js:1


---

### Takeaway

The whole concept of JavaScript Hoisting lies in the creation of Execution Context 

- Even before the first line is executed JavaScript has reserved the memory for the variables.

    [image](images/varReservedStorage.jpg)

- For the function, it stores the whole code (actual copy of the function) instead of reserving the memory space as undefined.

    [image](images/functionReservedStorage.jpg)