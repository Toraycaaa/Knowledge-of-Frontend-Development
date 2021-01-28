## [剑指 Offer 58] 左旋转字符串 ##

![1609977059699](C:\Users\lizhiyao\AppData\Roaming\Typora\typora-user-images\1609977059699.png)

> 思路一

字符串转化为数组（**.split(""**) —— 将数组的第一个元素添加到最后一个位置并删除(**.shift()**) —— 循环n次—— 数组转化为字符串输出(**.join("")**)

```js
// 1.
var reverseLeftWords = function(s, n) {
    let newS = s.split("")
    for (let i = 0; i < n; i++) {
        let move = newS.shift()
        newS.push(move)
    }
    return newS.join("")
};
```

Result：

执行用时：**92** ms, 在所有 JavaScript 提交中击败了**30.34%**的用户

内存消耗：**40.8** MB, 在所有 JavaScript 提交中击败了**15.81%**的用户

**复杂度为 O(n) 结果不尽如人意** 

> 优化思路二 —— 减少转换数组的过程

取前n个元素(**.substring(0,n)**) —— 删除前n个元素(**.substr(start，length)**) —— 连接两段字符串(**.concat()**亦可以用 **+**)

``` js
var reverseLeftWords = function(s, n) {
    return s.substr(n).concat(s.substring(0,n))
};
```

Result:

执行用时：80 ms, 在所有 JavaScript 提交中击败了79.39%的用户

内存消耗：39.1 MB, 在所有 JavaScript 提交中击败了74.88%的用户

**复杂度为O(n)具体复杂度不会算

> 其他思路三 ——  列表遍历拼接（若面试规定不允许使用 **切片函数** ，则使用此方法。 ）

算法流程：

1. 新建一个 list(Python)、StringBuilder(Java) ，记为 resres ；
2. 先向 res 添加 “第 n + 1 位至末位的字符” ；
3. 再向 res 添加 “首位至第 n 位的字符” ；
4. 将 res 转化为字符串并返回。

 ![Picture2.png](https://pic.leetcode-cn.com/5d1b29cce931ef9f42aab53435e8ba834ce9fe47df87df744c6568125112aae1-Picture2.png) 

> 其他思路四 —— 巧妙反转

https://leetcode-cn.com/problems/zuo-xuan-zhuan-zi-fu-chuan-lcof/solution/yuan-di-ju-bu-fan-zhuan-zheng-ti-fan-zhuan-xiang-j/

这道题目也非常类似，依然可以通过局部反转+整体反转 达到左旋转的目的。

具体步骤为：

1. 反转区间为前n的子串
2. 反转区间为n到末尾的子串
3. 反转整个字符串

 ![剑指Offer58-II.左旋转字符串.png](https://pic.leetcode-cn.com/1599203229-TUcYHl-%E5%89%91%E6%8C%87Offer58-II.%E5%B7%A6%E6%97%8B%E8%BD%AC%E5%AD%97%E7%AC%A6%E4%B8%B2.png) 

**本方法空间复杂度为O(1)**

