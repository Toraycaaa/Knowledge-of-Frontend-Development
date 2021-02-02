## [1 day & 1 Quiz] #2

***

**Question:**

What's the output? 

```js
for (var i = 0; i < 3; i++) {
  setTimeout(() => console.log(i), 1);
}

for (let i = 0; i < 3; i++) {
  setTimeout(() => console.log(i), 1);
}
```

- A: `0 1 2` and `0 1 2`
- B: `0 1 2` and `3 3 3`
- C: `3 3 3` and `0 1 2`

**Answer:** C

Because of the event queue in JavaScript, the `setTimeout` callback function is called *after* the loop has been executed. Since the variable `i` in the first loop was declared using the `var` keyword, this value was global. During the loop, we incremented the value of `i` by `1` each time, using the unary operator `++`. By the time the `setTimeout` callback function was invoked, `i` was equal to `3` in the first example.

In the second loop, the variable `i` was declared using the `let` keyword: variables declared with the `let` (and `const`) keyword are block-scoped (a block is anything between `{ }`). During each iteration, `i` will have a new value, and each value is scoped inside the loop.

**Tips:**

Asynchronous & synchronous in JS

![1612081156661](C:\Users\lizhiyao\AppData\Roaming\Typora\typora-user-images\1612081156661.png)

JavaScript is ==a non-blocking single thread== which use the ==Message queue== and ==Event loop== to handle asynchronous operations.

setTimeout():

The effect of  `setTimeout`is inserting the callback function into the message after a certain time. After all synchronous tasks have been completed, handle the callback function. 'Cause the synchronous operations will cost time, so the waiting time is more than certain time.

 ![img](https://user-gold-cdn.xitu.io/2018/1/26/161314dcb17a84ad?imageView2/0/w/1280/h/960/format/webp/ignore-error/1) 

**Reference**: https://juejin.cn/post/6844903556084924423