## [1 day & 1 Quiz] #5

***

**Question:**

Which one is correct?

```js
const bird = {
  size: 'small'
}

const mouse = {
  name: 'Mickey',
  small: true
}
```

- A: `mouse.bird.size`is unavailable
- B: `mouse[bird.size]`is unavailable
- C: `mouse[bird["size"]]`is unavailable

**Answer:** A

https://mp.weixin.qq.com/s/zrJBWkpO9-yEOxkcxqWVKw

`mouse[bird.size]` => `mouse["small"]` => `true`

`mouse[bird["size"]]`=>`mouse["small"]` => `true`

In JS, all of keys of Object are String(excluding Symbol Object).

[] => from right to left, . => from right to left, the object - mouse doesn't have a object named bird, so the A is not available.