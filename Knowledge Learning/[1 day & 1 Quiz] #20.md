

## [1 day & 1 Quiz] #20

***

*16/02/2021*

**Question:**

What's the output? 

```js
function getAge() {
  'use strict';
  age = 21;
  console.log(age);
}

getAge();
```

- A: `21`
- B: `undefined`
- C: `ReferenceError`
- D: `TypeError`

**Answer:** C

With `"use strict"`, you can make sure that you don't accidentally declare global variables. We never declared the variable `age`, and since we use `"use strict"`, it will throw a reference error. If we didn't use `"use strict"`, it would have worked, since the property `age` would have gotten added to the global object. 

`undefined`: the variable is declared but is not yet bind any value.

`ReferenceError`: the variable is not yet declared. JS could not find it.

```js
let a = b; // ReferenceError，因为 b 未被定义
console.log(c) // ReferenceError，因为 c 未被定义
```

`TypeError`: The object don't have the method or variable. 

```js
let a; // a = undefined
console.log(a.b) // TypeError,无法从 undefined 这个类型上读取属性

let c = 1;
console.log(c()) // TypeError，c并不是一个函数
```

