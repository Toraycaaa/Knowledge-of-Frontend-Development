## [LC.66] Plus One

***

> Solution 1:  hard code to imitate carry over next place

```js
//1.
var digits = [1,9,9,2,9,9];
var plusOne = function(digits) {
	let next = false
	let reverseDigits = digits.reverse()
	reverseDigits.push(0)
	if (reverseDigits[0] === 9){
			next = true
			reverseDigits[0] = 0
			for (let i=1;i<reverseDigits.length;i++){
				if(next === true){
					if(reverseDigits[i]=== 9){
						reverseDigits[i] = 0
					}else{
						reverseDigits[i]++
						next = false
						break
					}
				}else{
					break
				}
			}
	}else{
		reverseDigits[0]++
	}
	if(reverseDigits[reverseDigits.length-1] === 0){
		reverseDigits.pop()
	}
	return reverseDigits.reverse()
};
```

Result:

执行用时：88 ms, 在所有 JavaScript 提交中击败了41.73%的用户

内存消耗：37.8 MB, 在所有 JavaScript 提交中击败了78.78%的用户

Time Complexity: O(n)

Space Complexity: O(n)



> use arr.unshift()

```js
//3.
var plusOne = function(digits) {
  for (let i = digits.length - 1; i >=0; i--) {
    digits[i]++;
    digits[i] = digits[i] % 10;
    if (digits[i] > 0) {
      return digits;
    }
  }
  digits.unshift(1);
  return digits;
};
```

arr.unshift() : add a new element at the head of array and return the current length of array

arr.shift(): delete & return the head of array