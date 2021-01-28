## [LC.75] Sort Colors

***

> Requirement

Could you solve this problem without using the library's sort function?
Could you come up with a one-pass algorithm using only O(1) constant space?

> Solution 1: Map

```js
var sortColors = function(nums) {
    let map = new Map
    let res = []
    map.set(0,[])
    map.set(1,[])
    map.set(2,[])
    for(let i = 0; i<nums.length;i++){
        switch (nums[i]){
            case 0: 
                map.set(0,[...map.get(0),i])
                break
            case 1: 
                map.set(1,[...map.get(1),i])
                break
            case 2: 
                map.set(2,[...map.get(2),i])
                break
        }
    }
    for (let i = 0;i<3;i++){
        for (let j = 0;j<map.get(i).length;j++){
            res.push(i)
        }
    }
    return res
};
```

Time Complexity: O(n)

Space Complexity: O(n)

Don't meet the requirement.

> Solution 2: 2-pass

Idea:  通过两次遍历，第一遍遍历首先将 1 归位，第二遍遍历将 0 归位，自然 2 也就被归位了.

```js
var sortColors = function(nums) {
    for (let i=0;i<nums.length;i++){
        if (nums[i] === 1){
                nums.splice(i,1);
                nums.unshift(1)            
                }
    }
    for (let i=0;i<nums.length;i++){
        if (nums[i] === 0){
            nums.splice(i,1);
            nums.unshift(0)
            }
    }
    return nums
};
```

Result:

执行用时：76 ms, 在所有 JavaScript 提交中击败了94.84%的用户

内存消耗：37.7 MB, 在所有 JavaScript 提交中击败了73.15%的用户

Time Complexity: O(2n)

Space Complexity: O(1)

> Solution 3: 1-pass

```js
//2.
var swap = function (nums,i,j){
    let temp = nums[i]
    nums[i] = nums[j]
    nums[j] = temp
}
var sortColors = function(nums) {
    let len = nums.length
    let left = 0
    let right = len - 1
    //注意循环停止的条件，别忘了<=   [2,0,1]会有bug
    for (let i=0;i<=right;i++){
        if(nums[i]===0){
            swap(nums,i,left)
            left++
        }
        if(nums[i]===2){
            swap(nums,i,right)
            right--
            //如果当前元素不为1，则继续判断当前位置元素
            if(nums[i] !== 1){
                i--
            }
        }
    }
    return nums
}
```

Idea: quick sort & partition

Result:

执行用时：76 ms, 在所有 JavaScript 提交中击败了94.84%的用户

内存消耗：37.8 MB, 在所有 JavaScript 提交中击败了63.85%的用户