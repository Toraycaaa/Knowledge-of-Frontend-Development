## [1 day & 1 Quiz] #4

***

**Question:**

What's the output? 

```js
+true;
!'Lydia';
```

- A: `1` and `false`
- B: `false` and `NaN`
- C: `false` and `false`

**Answer:** A

The unary plus tries to convert an operand to a number. `true` is `1`, and `false` is `0`.

The string `'Lydia'` is a truthy value. What we're actually asking, is "is this truthy value falsy?". This returns `false`.

**Tips: **In JS, there are key words which equal to false, **0, [], "", "0",["0"],** and **undefined, NaN** is not equal to false or true.