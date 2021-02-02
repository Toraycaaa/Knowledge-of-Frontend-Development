## [1 day & 1 Quiz] #6

***

**Question:**

 What's the output? 

```js
let c = { greeting: 'Hey!' };
let d;

d = c;
c.greeting = 'Hello';
console.log(d.greeting);
```

- A: `Hello`
- B: `Hey!`
- C: `undefined`
- D: `ReferenceError`
- E: `TypeError`

**Answer:** A

Deep copy & shallow copy

In JavaScript, all objects interact by *reference* when setting them equal to each other.

First, variable `c` holds a value to an object. Later, we assign `d` with the same reference that `c` has to the object.

When you change one object, you change all of them. 

[![img](https://camo.githubusercontent.com/7fa22323daec0bc9742948c600eb9d951d28488132dcfb47e181d8b0a92b5f6e/68747470733a2f2f692e696d6775722e636f6d2f6b6f356b3066732e706e67)](https://camo.githubusercontent.com/7fa22323daec0bc9742948c600eb9d951d28488132dcfb47e181d8b0a92b5f6e/68747470733a2f2f692e696d6775722e636f6d2f6b6f356b3066732e706e67)