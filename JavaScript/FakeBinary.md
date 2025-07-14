# Fake Binary

## Problem
Given a string of digits, you should replace any digit below 5 with '0' and any digit 5 and above with '1'. Return the resulting string.

Note: input will never be an empty string

## Solution
```javascript
 function fakeBin(x){ 
  let newX = ""; 
  for (let i = 0; i <= x.length - 1; i++) { 
    if (parseInt(x[i]) < 5) { 
      newX += "0"; 
    } 
    else { 
      newX += "1"; 
    } 
  } 
  return newX; 
} 
```
