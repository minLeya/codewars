# Take an Arrow to the knee, Functionally

## Problem
Come here to practice the Arrow style functions Not much else to say good luck!
Details
You will be given an array of numbers which can be used using the String.fromCharCode() (JS), Tools.FromCharCode() (C#) method to convert the number to a character. It is recommended to map over the array of numbers and convert each number to the corresponding ascii character.

## Solution
```javascript
const arrowFunc = function(arr) {
  return arr.map( n => String.fromCharCode(n) ).join(''); //Complete this function
}
```

## Reference
```javascript
const materials = ["Hydrogen", "Helium", "Lithium", "Beryllium"];

console.log(materials.map((material) => material.length));
// Expected output: Array [8, 6, 7, 9]

```
