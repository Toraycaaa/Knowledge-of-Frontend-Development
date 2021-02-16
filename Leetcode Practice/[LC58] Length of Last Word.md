## [LC.58] [Length of Last Word](https://leetcode-cn.com/problems/length-of-last-word/) ##

**[Easy]**

![1612351645001](C:\Users\lizhiyao\AppData\Roaming\Typora\typora-user-images\1612351645001.png)

> Solution 1: brute force 

```js
//1.brute force
var lengthOfLastWord = function(s) {
    //remove two sider
    let temp = s.trim()
    //aviod "  "
    if(temp.length===0){
        return 0
    }
    let res = temp.split(" ")
    return res[res.length-1].length
};
```

**Answer**

https://github.com/LiangJunrong/document-library/blob/master/%E7%B3%BB%E5%88%97-LeetCode/%E9%9A%BE%E5%BA%A6%E5%88%92%E5%88%86/easy/058-%E6%9C%80%E5%90%8E%E4%B8%80%E4%B8%AA%E5%8D%95%E8%AF%8D%E7%9A%84%E9%95%BF%E5%BA%A6%EF%BC%88length-of-last-word%EF%BC%89.md

**Result**

执行用时：84 ms, 在所有 JavaScript 提交中击败了55.63%的用户

内存消耗：37.8 MB, 在所有 JavaScript 提交中击败了59.04%的用户

Time Complexity: O(n)

Space Complexity: O(n)

> Solution: Regular Expression

```js
var lengthOfLastWord = function(s) {
  s = s.replace(/(\s*$)/g, "");
  let arr = s.split(' ');
  return arr[arr.length - 1].length;
};
```







