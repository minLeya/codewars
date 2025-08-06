# Minimize Sum Of Array (Array Series #1)


## Problem
Given an array of integers , Find the minimum sum which is obtained from summing each Two integers product.

Input >> Output Examples  
minSum({5,4,2,3}) ==> return (22)   
Explanation:  
The minimum sum obtained from summing each two integers product ,  5*2 + 3*4 = 22  


minSum({12,6,10,26,3,24}) ==> return (342)  
Explanation:  
The minimum sum obtained from summing each two integers product ,  26*3 + 24*6 + 12*10 = 342  


minSum({9,2,8,7,5,4,0,6}) ==> return (74)
Explanation:
The minimum sum obtained from summing each two integers product ,  9*0 + 8*2 +7*4 +6*5 = 74


## Solution №1
```javascript
function minSum(arr) {
  arr.sort((a, b) => a - b);
  let sum = 0;
  for (let i = 0; i < arr.length / 2; i++) {
    sum += arr[i] * arr[arr.length - 1 - i];
    console.log(arr[i] + "  " + arr[arr.length - 1 - i]);
  }
  return sum;
}
```

## Solution №2
```javascript
const minSum = arr =>
  arr.sort((a, b) => a - b).reduce((pre, val) => pre + val * arr.pop(), 0);
```
