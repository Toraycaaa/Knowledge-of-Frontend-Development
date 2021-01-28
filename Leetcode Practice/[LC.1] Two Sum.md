## [LC.1] Two Sum ##

Answer:

https://github.com/LiangJunrong/document-library/blob/master/%E7%B3%BB%E5%88%97-LeetCode/%E9%9A%BE%E5%BA%A6%E5%88%92%E5%88%86/easy/001-%E4%B8%A4%E6%95%B0%E4%B9%8B%E5%92%8C%EF%BC%88two-sum%EF%BC%89.md

![1610405451270](C:\Users\lizhiyao\AppData\Roaming\Typora\typora-user-images\1610405451270.png)

> Solution 1: brute force 

```js
//1.brute force
var twoSum = function(nums, target) {
    for (let i = 0; i < nums.length; i++) {
    //for (let i in nums) {
        let tar = target - nums[i]
        if (nums.indexOf(tar,i+1) !== -1){
            return [i,nums.indexOf(tar,i+1)]
        }
    }
};
```

**Idea:**

Find the difference between the first element and target and find it from the rest of array.

arr.indexOf(target, start): find the target from the start index

**Result:**

执行用时：72 ms, 在所有 JavaScript 提交中击败了98.07%的用户

内存消耗：37.9 MB, 在所有 JavaScript 提交中击败了78.11%的用户

Time complexity: O(n^2^) 

Space complexity: O(1)

> Solution 2: hash map - object

Idea: loop the array -> search the element as key in the dictionary -> if it's exist, return the value of dic and the index of array, else add a new element into the dic which key is the difference between target and the current element of array and which value is the index.

Coding:

```js
//2.dictionary - object
var twoSum = function(nums, target) {
    let dic = new Object
    for (let i=0;i<nums.length;i++){
        if (dic[nums[i]] || dic[nums[i]] === 0){
			return [dic[nums[i]],i]
        }else{
            dic[target - nums[i]] = i			
        }
    }
};
```

Result: 

执行用时：72 ms, 在所有 JavaScript 提交中击败了97.99%的用户

内存消耗：37.9 MB, 在所有 JavaScript 提交中击败了79.93%的用户

Time complexity: O(n)

Space complexity: O(n)

**ECMAScript 6 new feature -- Map**

Introduction:

https://github.com/LiangJunrong/document-library/blob/master/JavaScript-library/JavaScript/%E5%86%85%E7%BD%AE%E5%AF%B9%E8%B1%A1/Map/README.md

Code:

```js
//3.dictionary - Map
var twoSum = function(nums, target) {
    let dic = new Map
    for (let i=0;i<nums.length;i++){
        if (dic.has(nums[i])){
            return [dic.get(nums[i]),i]
        }else{
            dic.set(target - nums[i],i)
        }
    }
}
```

Result: 

执行用时：76 ms, 在所有 JavaScript 提交中击败了94.02%的用户

内存消耗：37.9 MB, 在所有 JavaScript 提交中击败了85.35%的用户







