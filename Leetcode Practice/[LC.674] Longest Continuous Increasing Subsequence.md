## [LC.674] [Longest Continuous Increasing Subsequence](https://leetcode-cn.com/problems/longest-continuous-increasing-subsequence/) & The sliding window algorithm

***

> Solution 1: 1-pass and 2-pointers

**Idea:** pass the array and record the continuous increasing subsequence and choose the longest one, finally deal with some abnormal situation.

```js
var findLengthOfLCIS = function(nums) {
    if(nums.length===0){
        return 0
    }
    let curRes = 1
    let res = 1
    for (let i=1;i<nums.length;i++){
        if (nums[i]>nums[i-1]){
            curRes++
        }else if(res<curRes){
            res = curRes
            curRes = 1
        }else{
            curRes = 1
        }
    }
    return res>curRes? res:curRes
};
```

**Result: **

执行用时：84 ms, 在所有 JavaScript 提交中击败了71.62%的用户

内存消耗：38.5 MB, 在所有 JavaScript 提交中击败了69.74%的用户

Time Complexity: O(n)

Space Complexity: O(1)

 ![img](https://i3.hoopchina.com.cn/blogfile/20211/24/BbsImg_242888601160761_1611454767_s_6732417_o_w_1600_h_900_39322.gif) 

> Solution 2:  Sliding Window 

```js
const findLengthOfLCIS = (nums) => {
  let result = 0, 
      position = 0; //the start of sliding window
  for (let i = 0; i < nums.length; i++) {
    if (i > 0 && nums[i] < nums[i - 1]) {
      //move the pointer to the current index
      position = i;
    }
    //compare the length of sliding windows & res
    result = Math.max(result, i - position + 1);
  }
  return result;
};
```

https://github.com/LiangJunrong/document-library/blob/master/%E7%B3%BB%E5%88%97-LeetCode/%E9%9A%BE%E5%BA%A6%E5%88%92%E5%88%86/easy/674-%E6%9C%80%E9%95%BF%E8%BF%9E%E7%BB%AD%E9%80%92%E5%A2%9E%E6%95%B0%E5%88%97%EF%BC%88longest-continuous-increasing-subsequence%EF%BC%89.md



**Sliding Window algorithm:** 

https://www.zhihu.com/question/314669016

it will solve the subsequence questions, converting duplicate loops(O(n^2^)) to single loop(O(n)) to reduce the time complexity.

> **Sliding window example 1:** 

Given a array of integers, calculate the longest continuous subsequence

Input: arr [] = {100,200,300,400}, k = 2

Output: 700

 ![img](https://pic2.zhimg.com/80/v2-98bc2f4a5ea853dd8cff43f252cbf519_720w.jpg?source=1940ef5c) 

```js
function maxSum(arr, k) {
  const n = arr.length;
  if (n < k) {
    return -1;
  }
  // calculate the value in the first window
  let maxSum = 0;
  for (let i = 0; i < k; i++) {
    maxSum += arr[i];
  }

  let sum = maxSum;
  for (let i = k; i < n; i++) {
    // 新窗口的和 = 前一个窗口的和 + 新进入窗口的值 - 移出窗口的值
    sum += arr[i] - arr[i - k];
    maxSum = Math.max(maxSum, sum);
  }
  return maxSum;
}
```

> **Sliding window example 2:** [LC.76] [Minimum Window Substring](https://leetcode-cn.com/problems/minimum-window-substring/)[HARD]

 

给定一个字符串 S 和一个字符串 T，请在 S 中找出包含 T 所有字母的最小子串。(minimum-window-substring) 

Given a string S and a string T, find the minimum substring including T from S

```text
Input: S = "ADOBECODEBANC", T = "ABC"
Output: "BANC"
```