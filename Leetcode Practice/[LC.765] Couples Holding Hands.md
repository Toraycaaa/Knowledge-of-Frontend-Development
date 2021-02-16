## [LC.765] [Couples Holding Hands](https://leetcode-cn.com/problems/couples-holding-hands/) ##

*14/02/2021*

**[Hard]**

![1613441779148](C:\Users\lizhiyao\AppData\Roaming\Typora\typora-user-images\1613441779148.png)

> Solution 1: Greedy Algorithm

```js
var minSwapsCouples = function(row) {
    let count = 0
    for (let i=0;i<row.length;i+=2){
		
        if(checkCouple(i,i+1,row)){
            continue
        }else{
            if(row[i]%2 === 0){
                let index = row.indexOf(row[i]+1)
                swap(i+1,index,row)
                count++
            }else if(row[i]%2 === 1){
				let index = row.indexOf(row[i]-1)
                swap(i+1,index,row)
                count++
			}
        }
    }
    return count
};
function swap (i,j,row){
    [row[i],row[j]] = [row[j],row[i]]
    console.log([row[i],row[j]])
}
function checkCouple (i,j,row){
    if(row[i]%2 === 0 && row[j]===row[i]+1){
        return true
    }else if(row[i]%2 === 1 && row[j]===row[i]-1){
        return true
    }else{
        return false
    }
}
```

**Idea:**

Pass the array with even indexes, and find their partner number, then swap them.

 ![765.gif](https://pic.leetcode-cn.com/1613269893-FrLpuk-765.gif) 

**Result:**

执行用时：92 ms, 在所有 JavaScript 提交中击败了12.50%的用户

内存消耗：39.9 MB, 在所有 JavaScript 提交中击败了6.25%的用户

Time complexity: O(n^2^) 

Space complexity: O(1)

> Solution 2: Disjoint-set data structure 
>
> Solution 3: Hash map
>
> Solution 4: DFS

