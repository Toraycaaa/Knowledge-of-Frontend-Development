



## [1 day & 1 Quiz] #10

***

*30/01/2021*

**Question:**

What happens when we do this? 

```js
function bark() {
  console.log('Woof!');
}

bark.animal = 'dog';
```

- A: Nothing, this is totally fine!
- B: `SyntaxError`. You cannot add properties to a function this way.
- C: `"Woof"` gets logged.
- D: `ReferenceError`

**Answer:** A

This is possible in JavaScript, because functions are objects! (**Everything besides primitive types are objects**)

A function is a special type of object. The code you write yourself isn't the actual function. The function is an object with properties. This property is invocable.

**Tip:**

==A function is a special object!!!==

Call: bark()

Invoke: bark.animal

In case of **Calling**, you originally refer to the statement that actually calls the function.

In case of **Invoking**, you indirectly refer to calling statement to actually invoke/run the function.

Reference: https://stackoverflow.com/questions/50884893/calling-vs-invoking-a-function

