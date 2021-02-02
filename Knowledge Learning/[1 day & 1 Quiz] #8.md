



## [1 day & 1 Quiz] #8

***

**Question:**

What's the output? 

```js
class Chameleon {
  static colorChange(newColor) {
    this.newColor = newColor;
    return this.newColor;
  }

  constructor({ newColor = 'green' } = {}) {
    this.newColor = newColor;
  }
}

const freddie = new Chameleon({ newColor: 'purple' });
console.log(freddie.colorChange('orange'));
```

- A: `orange`
- B: `purple`
- C: `green`
- D: `TypeError`

The `colorChange` function is static. Static methods are designed to live only on the constructor in which they are created, and cannot be passed down to any children. Since `freddie` is a child, the function is not passed down, and not available on the `freddie` instance: a `TypeError` is thrown. 

**Tip:**

`freddie.colorChange()` is false, `Chameleon.colorChange()` is true.

The search path of `freddie.colorChang()` is `freddit - &gt;__proto__ - &gt;__proto__ - ...`

The search path of `Chameleon.colorChange()` is `freddit- &gt;__proto__ - &gt;construtor - &gt;colorChange`

A constructor which allow declaration without parameter:

```js
constructor({ newColor = 'green' } = {}) {
    this.newColor = newColor;
  }
}
```



`static` keyword: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes/static

Classes in JS: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes

