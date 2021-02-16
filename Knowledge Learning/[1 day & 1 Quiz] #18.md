

## [1 day & 1 Quiz] #18

***

*14/02/2021*

**Question:**

What's the output? 

```js
function checkAge(data) {
  if (data === { age: 18 }) {
    console.log('You are an adult!');
  } else if (data == { age: 18 }) {
    console.log('You are still an adult.');
  } else {
    console.log(`Hmm.. You don't have an age I guess`);
  }
}

checkAge({ age: 18 });
```

- A: `You are an adult!`
- B: `You are still an adult.`
- C: `Hmm.. You don't have an age I guess`

**Answer:** C

When testing equality, primitives are compared by their *value*, while **objects are compared by their *==reference==***. JavaScript checks if the objects have a ==reference== to the same location in memory.

The two objects that we are comparing don't have that: the object we passed as a parameter refers to a different location in memory than the object we used in order to check equality.

This is why both `{ age: 18 } === { age: 18 }` and `{ age: 18 } == { age: 18 }` return `false`.

**Objects are compared with their location in memory(Reference).**

