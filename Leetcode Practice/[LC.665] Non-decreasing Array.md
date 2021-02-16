## [LC.665] [Non-decreasing Array](https://leetcode-cn.com/problems/non-decreasing-array/)

Answer:



![1612695576271](C:\Users\lizhiyao\AppData\Roaming\Typora\typora-user-images\1612695576271.png)

> Solution 1: 

```js
var checkPossibility = function(nums) {
    const n = nums.length;
    for (let i = 0; i < n - 1; ++i) {
        const x = nums[i], y = nums[i + 1];
        if (x > y) {
            nums[i] = y;
            if (isSorted(nums)) {
                return true;
            }
            nums[i] = x; // 复原
            nums[i + 1] = x;
            return isSorted(nums);
        }
    }
    return true;
};

const isSorted = (nums) => {
    const n = nums.length;
    for (let i = 1; i < n; ++i) {
        if (nums[i - 1] > nums[i]) {
            return false;
        }
    }
    return true;
}
```



**Result:**

执行用时：84 ms, 在所有 JavaScript 提交中击败了92.89%的用户

内存消耗：40.6 MB, 在所有 JavaScript 提交中击败了58.45%的用户

Time complexity: O(2n) 

Space complexity: O(1)

> Solution 2: Improvement

Coding:

```js
var checkPossibility = function(nums) {
    const n = nums.length;
    let cnt = 0;
    for (let i = 0; i < n - 1; ++i) {
        const x = nums[i], y = nums[i + 1];
        if (x > y) {
            cnt++;
            if (cnt > 1) {
                return false;
            }
            if (i > 0 && y < nums[i - 1]) {
                nums[i + 1] = x;
            }
        }
    }
    return true;
};
```

Result: 

执行用时：72 ms, 在所有 JavaScript 提交中击败了97.99%的用户

内存消耗：37.9 MB, 在所有 JavaScript 提交中击败了79.93%的用户

Time complexity: O(n)

Space complexity: O(1)

