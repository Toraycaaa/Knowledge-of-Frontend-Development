



## [1 day & 1 Quiz] #9

***

**Question:**

What's the output? 

```js
let greeting;
greetign = {}; // Typo!
console.log(greetign);
```

- A: `{}`
- B: `ReferenceError: greetign is not defined`
- C: `undefined`

**Answer:** A

It logs the object, because we just created an empty object on the global object! When we mistyped `greeting` as `greetign`, the JS interpreter actually saw this as `global.greetign = {}` (or `window.greetign = {}` in a browser).

In order to avoid this, we can use `"use strict"`. This makes sure that you have declared a variable before setting it equal to anything.

**Tip:**

Strict Mode &  **[sloppy mode](https://developer.mozilla.org/docs/Glossary/Sloppy_mode)** : https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Strict_mode

