## [LC.268] [Missing Number](https://leetcode-cn.com/problems/missing-number/) ##

**[Easy]**

**Answer:**https://github.com/LiangJunrong/document-library/blob/master/%E7%B3%BB%E5%88%97-LeetCode/%E9%9A%BE%E5%BA%A6%E5%88%92%E5%88%86/easy/268-%E7%BC%BA%E5%A4%B1%E6%95%B0%E5%AD%97%EF%BC%88missing-number%EF%BC%89.md

![1613295478359](C:\Users\lizhiyao\AppData\Roaming\Typora\typora-user-images\1613295478359.png)

> Solution 1: Sort

```js
//1.Sort
var missingNumber1 = function(nums) {
    nums = nums.sort(function(a,b){return a-b})
    for(let i=0;i<nums.length;i++){
        if(i !== nums[i]){
            return i
        }
    }
    return nums.length
};
```

**Result**

执行用时：116 ms, 在所有 JavaScript 提交中击败了30.71%的用户

内存消耗：40.1 MB, 在所有 JavaScript 提交中击败了64.33%的用户

Time Complexity: O(n)

Space Complexity: O(n)

> Solution:  Gauss's sum law 

**Gauss's sum law**: ==n(n+1)/2==

```js
//math
var missingNumber2 = function(nums) {
    let sum = (1 + nums.length) * nums.length /2
    let result = 0
    for(let i=0;i<nums.length;i++){
        result = result + nums[i]
    }
    return sum-result
}
```

> Solution: XOR Bitwise operation

```js
var missingNumber = function(nums) {
    let result = nums.length
    for(let i=0;i<nums.length;i++){
        result = result ^ nums[i] ^ i
    }
    return result
}
```

![1613296889479](C:\Users\lizhiyao\AppData\Roaming\Typora\typora-user-images\1613296889479.png)