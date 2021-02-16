## [LC.448] [Find All Numbers Disappeared in an Array](https://leetcode-cn.com/problems/find-all-numbers-disappeared-in-an-array/) ##

**Answer:**

https://github.com/LiangJunrong/document-library/blob/master/%E7%B3%BB%E5%88%97-LeetCode/%E9%9A%BE%E5%BA%A6%E5%88%92%E5%88%86/easy/448-%E6%89%BE%E5%87%BA%E6%89%80%E6%9C%89%E6%95%B0%E7%BB%84%E4%B8%AD%E6%B6%88%E5%A4%B1%E7%9A%84%E6%95%B0%E5%AD%97%EF%BC%88find-all-numbers-disappeared-in-an-array%EF%BC%89.md

![1613258902766](C:\Users\lizhiyao\AppData\Roaming\Typora\typora-user-images\1613258902766.png)

> Solution 1: brute force 

```js
//1.brute force
var findDisappearedNumbers = function(nums) {
    let res = []
    nums = nums.sort()
    for (let i=0;i<nums.length;i++){
        if(!nums.includes(i+1)){
            res.push(i+1)
        }
    }
    return res
};
```

**Result:**

Time complexity: O(n^2^) 

Space complexity: O(1)

> Solution 2: Map & Set

Coding:

```js
//2.Map
const findDisappearedNumbers2 = (nums) => {
  let map = new Map();
  for (let i = 1; i <= nums.length; i++) {
    map.set(i, 1);
  }
  for (let j = 0; j < nums.length; j++) {
    if (map.get(nums[j])) {
      map.delete(nums[j]);
    }
  }
  let result = [];
  for (let key of map.keys()) {
    result.push(key);
  }
  return result;
};
```

```js
// Set
const findDisappearedNumbers = (nums) => {
  let newNums = [...new Set(nums)].sort((a, b) => a - b);
  let result = [];
  for (let i = 0; i < nums.length; i++) {
    if (newNums[i] != (i + 1)) {
      newNums.splice(i, 0, (i + 1));
      result.push((i + 1));
    }
  }
  return result;
};
```

**Result:** 

Time complexity: O(n)

Space complexity: O(n)

> Solution 3: Sort + Deduplicate

Code:

```js
//sort + dedupulicate
const findDisappearedNumbers4 = (nums) => {
  let len = nums.length
  let res = []
  nums = nums.sort(function(a,b){return a-b})
  for(let i=1;i<nums.length;i++){
      if (nums[i]===nums[i-1]){
          nums.splice(i,1)
          i--
      }
  }
  for(let i=0;i<len;i++){
      if(nums[i] !== i+1){
          nums.splice(i,0,-1)
      }
  }
  for(let i=0;i<len;i++){
      if(nums[i] !== i+1){
          res.push(i+1)
      }
  }
  return res
};
```

**Result:** 

Time complexity: O(n)

Space complexity: O(n)

> Solution 4: Optimistic Solution

```js
var findDisappearedNumbers5 = function(nums) {
  let result = []
  for (let i=0;i<nums.length;i++){
      if(nums[Math.abs(nums[i])-1]>0){
        nums[Math.abs(nums[i])-1] = nums[Math.abs(nums[i])-1] * -1
      }
  }
  for (let i=0;i<nums.length;i++){
      if(nums[i]>0){
          result.push(i+1)
      }
  }
  return result
};
```

**Idea:**

 ![448.gif](https://pic.leetcode-cn.com/1613182887-IlNpfN-448.gif) 

**Result:**

执行用时：168 ms, 在所有 JavaScript 提交中击败了38.69%的用户

内存消耗：45.6 MB, 在所有 JavaScript 提交中击败了91.19%的用户

Time Complexity: O(n)

Space Complexity: O(1)



