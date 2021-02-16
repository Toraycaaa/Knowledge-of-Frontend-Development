

## [1 day & 1 Quiz] #19

***

*14/02/2021*

**Question:**

What's the output? 

```js
function getAge(...args) {
  console.log(typeof args);
}

getAge(21);
```

- A: `"number"`
- B: `"array"`
- C: `"object"`
- D: `"NaN"`

**Answer:** C

 The rest parameter (`...args`) lets us "collect" all remaining arguments into an array. An array is an object, so `typeof args` returns `"object"` 

The **destructuring assignment** syntax:

https://www.jianshu.com/p/5fccba8328e3

