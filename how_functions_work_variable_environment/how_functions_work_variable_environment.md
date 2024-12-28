---
type: Programming
title: Namaste JavaScript Ep. 4
description: How functions work in JS ❤️ & Variable Environment
tags: [JavaScript]
timestamp: '2024-12-27'
resource: '[https://www.youtube.com/watch?v=gSDncyuGw0s&list=PLlasXeu85E9cQ32gLCvAvr9vNaUccPVNP&index=5](https://www.youtube.com/watch?v=gSDncyuGw0s&list=PLlasXeu85E9cQ32gLCvAvr9vNaUccPVNP&index=5)'
difficulty: Unraked
---

### Lesson Main Point

Function's ExeContexts are independent and even if you have the var with the same name their environments are different due to the separate ExeContext.

After executing the whole program, the Global ExeContext pops out of the Call Stack 

### Short Notes

---

```javascript
var x = 1; 
// can invoke the function even before the initialisation due to hoisting
a();
b();
console.log(x);

function a() {
  var x = 10;
  console.log(x);
}

function b() {
  var x = 100;
  console.log(x);
}
```


---

> Output:
​10
​100
​1


---

Creation of code -> call stack -> Global ExeContext (memory | code)

function invoked (Line 3) -> specific ExeContext for that specific function (independent) and pushed into the call stack and got the control (Line 7) -> Phase 1 and 2

Function runs line by line got to console.log(x) (Line 9) -> JavaScript looks for **x** in the local memory (function specific ExeContext's memory component)

Function execution finished --> the whole function ExeContext is gone and popped out of the Call Stack and the control goes back to Global ExeContext (Line 3)

**Line 4 -->** back to Global ExeContext and JavaScript looks for x in the Global Environment's Memory where it is declared as 1 (Line 1) and prints it as an output

### Takeaway

Code Execution and Environment depends on the concepts of **Execution Context** and **Hoisting**

Function creates their own ExeContext and pushes it into the Call Stack and popped out as soon as the execution is done. 

Function execution environments are independent (Local)

storage for var is reserved as *undefined* before the execution starts even though it is assigned at the very first line. (NOTE: Creation of Global ExeContext before execution is different from the actual execution of code | *reference: Phase 1 and Phase 2 concept*

Call Stack is clear after running the whole program


