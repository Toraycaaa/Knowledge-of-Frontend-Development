

## [1 day & 1 Quiz] #21

***

*17/02/2021*

**Question:**

What's the value of `sum`? 

```js
const sum = eval('10*10+5');
```

- A: `105`
- B: `"105"`
- C: `TypeError`
- D: `"10*10+5"`

**Answer:** A

## [Never use eval()!](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/eval#never_use_eval!)

 `eval` evaluates codes that's passed as a string. If it's an expression, like in this case, it evaluates the expression. The expression is `10 * 10 + 5`. This returns the number `105`. 

```js
console.log(eval('2 + 2'));
// expected output: 4

console.log(eval(new String('2 + 2')));
// expected output: 2 + 2

console.log(eval('2 + 2') === eval('4'));
// expected output: true

console.log(eval('2 + 2') === eval(new String('2 + 2')));
// expected output: false
```

