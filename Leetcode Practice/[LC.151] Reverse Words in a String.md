## [LC.151] [Reverse Words in a String](https://leetcode-cn.com/problems/reverse-words-in-a-string/) ##

**[Medium]**

Answer:https://github.com/LiangJunrong/document-library/blob/master/%E7%B3%BB%E5%88%97-LeetCode/%E9%9A%BE%E5%BA%A6%E5%88%92%E5%88%86/medium/151-%E7%BF%BB%E8%BD%AC%E5%AD%97%E7%AC%A6%E4%B8%B2%E9%87%8C%E7%9A%84%E5%8D%95%E8%AF%8D%EF%BC%88reverse-words-in-a-string%EF%BC%89.md

![1612346234658](C:\Users\lizhiyao\AppData\Roaming\Typora\typora-user-images\1612346234658.png)

> Solution 1: 

```js
var reverseWords = function(s) {
    let res = []
    let subString = []
    for(let i=0;i<s.length;i++){
        if (s.charAt(i) !== ' '){
            subString = subString + s.charAt(i)
        }else{
            if(subString.length>0){
                res.push(subString)
                subString = []
            }
        }
    }
    if(subString.length>0){
        res.push(subString)
        subString = []
    }
    let output = res.reverse().join(' ')
    return output
};
```

> Shortest Answer

```js
var reverseWords = function(s) {
    return s.trim().split(/\s+/).reverse().join(' ');
};
```



Result:**

执行用时：88 ms, 在所有 JavaScript 提交中击败了50.48%的用户

内存消耗：39.7 MB, 在所有 JavaScript 提交中击败了19.70%的用户

Time complexity: O(n) 

Space complexity: O(n)

> Solution 3: Deque

```python
class Solution:
    def reverseWords(self, s: str) -> str:
        left, right = 0, len(s) - 1
        # 去掉字符串开头的空白字符
        while left <= right and s[left] == ' ':
            left += 1
        
        # 去掉字符串末尾的空白字符
        while left <= right and s[right] == ' ':
            right -= 1
            
        d, word = collections.deque(), []
        # 将单词 push 到队列的head & tail
        while left <= right:
            if s[left] == ' ' and word:
                d.appendleft(''.join(word))
                word = []
            elif s[left] != ' ':
                word.append(s[left])
            left += 1
        d.appendleft(''.join(word))
        
        return ' '.join(d)
```











