





## [1 day & 1 Quiz] #14

***

*13/02/2021*

**Question:**

 All object have prototypes. 

- A: true
- B: false

**Answer:** B

All objects have prototypes, except for the **base object**.

```js
 Object.getPrototypeOf(Function.prototype) === Object.prototype,
```

The base object is the object created by the user, or an object that is created using the `new` keyword. 

The base object has access to some methods and properties, such as `.toString`. This is the reason why you can use built-in JavaScript methods! All of such methods are available on the prototype. Although JavaScript can't find it directly on your object, it goes down the prototype chain and finds it there, which makes it accessible for you.  

### [Value properties](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects#value_properties)

### [Function properties](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects#function_properties)

[Fundamental objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects#fundamental_objects): 字符串（String）、数字(Number)、布尔(Boolean)、对空（Null）、未定义（Undefined）、Symbol。https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects

对象(Object)、数组(Array)、函数(Function)。

```js
typeof new Number(123); // 'object'
new Number(123) === 123; // false
```

```js
typeof new String('str'); // 'object'
new String('str') === 'str'; // false So, don't use it!
```

**Tips:**

**Value type** = 7 primitive values +  complex value(Object)

**Primitive values:** 

- [Boolean](https://developer.mozilla.org/zh-CN/docs/Glossary/Boolean)
- [Null](https://developer.mozilla.org/zh-CN/docs/Glossary/Null)
- [Undefined](https://developer.mozilla.org/zh-CN/docs/Glossary/undefined)
- [Number](https://developer.mozilla.org/zh-CN/docs/Glossary/Number)
- [BigInt](https://developer.mozilla.org/zh-CN/docs/Glossary/BigInt)
- [String](https://developer.mozilla.org/zh-CN/docs/Glossary/字符串)
- [Symbol](https://developer.mozilla.org/zh-CN/docs/Glossary/Symbol) 