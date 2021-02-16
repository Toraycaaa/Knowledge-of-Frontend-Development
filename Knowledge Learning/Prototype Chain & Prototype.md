##   Prototype Chain & Prototype

***

`__proto__`: for object, to find its properties and methods(a property of an object)

`prototype`: using for construct a `__proto__` of an object when we declare it.(a property of Function)

The object's `__proto__` store its contructor's prototype.

> Example 1

```js
var foo = {name:"A", age:"20"}
var bar = {name:"B", age:"25", job:"developer"}

foo.__proto__ = bar 
foo.job // "developer"
```

> Example 2

```js
var a = {
    x: 10,
    calucate: function(z){
        return this.x + this.y + z
    }
}

var b = {
    y:20,
    __proto__: a
}
var c = {
    y:30,
    __proto__: a
}
console.log(b.calculate(40)) //70   10+20+40
console.log(c.calculate(50)) //90   10+30+50
```

> Example 3

```js
function Foo(y){
    this.y = y
}

Foo.prototype.x = 100
Foo.prototype.calculate = function(z){
    return this.x + this.y + z
}

var b = new Foo(20) //initialize & declaration
var c = new Foo(30)

c.calculate(20) //150 100+30+20
b.__proto__ === Foo.prototype //true

//stem Source:
Object.prototype.__proto__ === null
Function.__proto__ === Function.prototype
Object.__proto__ === Function.__proto__

a.hasOwnProperty('a') //check whether it is a own property 
'a' in test//test(objec) check whether it is in prototye chain
```

