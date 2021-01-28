## [1 day & 1 Quiz] #7

***

**Question:**

Which one is correct?

```js
let a = 3
let b = new Number(3)
let c = 3
```

- A: true, false, true 
- B: false, false, true
- C: true, false, false
- D: false, true true

**Answer:** C

https://mp.weixin.qq.com/s/zrJBWkpO9-yEOxkcxqWVKw

`==` operation: just compare the value(0==false, ""=false, '0' == false, Boolean('0'), etc.)

`===`operation: compare the value and the type

`let a = 3` a is a number type, `Number(3)` is a function constructor, in fact, b is a Number Object.