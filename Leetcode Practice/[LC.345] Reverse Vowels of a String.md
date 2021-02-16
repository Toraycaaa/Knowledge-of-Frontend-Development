

## [LC.345] [Reverse Vowels of a String](https://leetcode-cn.com/problems/reverse-vowels-of-a-string/)



**[Easy]**

**Answer:**

https://github.com/LiangJunrong/document-library/blob/master/%E7%B3%BB%E5%88%97-LeetCode/%E9%9A%BE%E5%BA%A6%E5%88%92%E5%88%86/easy/345-%E5%8F%8D%E8%BD%AC%E5%AD%97%E7%AC%A6%E4%B8%B2%E4%B8%AD%E7%9A%84%E5%85%83%E9%9F%B3%E5%AD%97%E6%AF%8D%EF%BC%88reverse-vowels-of-a-string%EF%BC%89.md

![1612691785064](C:\Users\lizhiyao\AppData\Roaming\Typora\typora-user-images\1612691785064.png)



> Solution 1: 1-pass

```js
var reverseVowels = function(s) {
    let vowels = ["a","e","i","o","u","A","E","I","O","U"]
    let vowelList  = []
    let vowelIndex = []
    let tempS = s.split("")
    for(let i=0;i<tempS.length;i++){
        if(vowels.indexOf(tempS[i])>-1){
            vowelList.push(tempS[i])
            vowelIndex.push(i)
        }
    }
    let reverseVowels = vowelList.reverse()
    //pass the vowelIndex, replace the elements of s
    for(let i=0;i<vowelIndex.length;i++){
        tempS[vowelIndex[i]] = reverseVowels[i]
		
    }
	//console.log(tempS)
    let res = tempS.join("")
    return res
};
```

**Idea:**

Search the vowels and their index in the string, and reverse the vowels. Finally, re-fill back the string

**Result:**

执行用时：96 ms, 在所有 JavaScript 提交中击败了90.07%的用户

内存消耗：43.2 MB, 在所有 JavaScript 提交中击败了75.28%的用户

Time complexity: O(n) 

Space complexity: O(n)

> Solution 2: double pointers

Coding:

```js
var reverseVowels = function(s) {
    let leftPointer = 0
    let rightPointer = s.length-1
    s = s.split('');
    let vowels = ["a","e","i","o","u","A","E","I","O","U"]   
    while(leftPointer<rightPointer){ 
        if(!vowels.includes(s[leftPointer])){
            leftPointer++
            continue
        }
        if(!vowels.includes(s[rightPointer])){
            rightPointer--
            continue
        }
        [s[leftPointer],s[rightPointer]] = [s[rightPointer],s[leftPointer]]
		leftPointer++
        rightPointer--
    }
    return s.join('')
}
```

Result: 

执行用时：100 ms, 在所有 JavaScript 提交中击败了79.59%的用户

内存消耗：43.3 MB, 在所有 JavaScript 提交中击败了64.23%的用户

Time complexity: O(n)

Space complexity: O(1)

