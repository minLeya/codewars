# Find the missing element between two arrays

## Problem
Given two integer arrays where the second array is a shuffled duplicate of the first array with one element missing, find the missing element.

Please note, there may be duplicates in the arrays, so checking if a numerical value exists in one and not the other is not a valid solution.

```javascript
find_missing([1, 2, 2, 3], [1, 2, 3]) => 2
find_missing([6, 1, 3, 6, 8, 2], [3, 6, 6, 1, 2]) => 8
```

The first array will always have at least one element.  

## Solution №1
```javascript
function findMissing(arr1, arr2) {
  for (let el2 of arr2) {
    let index = arr1.indexOf(el2);
    if (index != -1) {
      arr1.splice(index, 1);
    }
  }
  return +arr1;
}

```

## Solution №2
```javascript
const findMissing = (arr1, arr2) => {
  arr1 = arr1.sort();
  arr2 = arr2.sort();
  for(let i = 0; i < arr1.length; i++){
    if(arr1[i] != arr2[i]) return arr1[i];
  }
}
```

## Solution №3
```javascript
function findMissing(arr1, arr2) {
   const reducer = (accumulator, currentValue) => accumulator + currentValue
return arr1.reduce(reducer, 0) - arr2.reduce(reducer, 0);
}
```

## Solution №4
```javascript
const sum = arr => arr.reduce((a, b) => a + b, 0);

const findMissing = (arr1, arr2) => sum(arr1) - sum(arr2);
```
