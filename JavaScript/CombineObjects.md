# Combine objects

## Problem
All input object properties will have only numeric values. Objects are combined together so that the values of matching keys are added together.

An example:
```javascript
const objA = { a: 10, b: 20, c: 30 }
const objB = { a: 3, c: 6, d: 3 }
combine(objA, objB) // Returns { a: 13, b: 20, c: 36, d: 3 }
```
The combine function should be a good citizen, so should not mutate the input objects.  


## Solution №1
```javascript
function combine(...objN) {
  return objN.reduce( (sum, object) => {
    for (let key in object) {
      sum[key] = (sum[key] || 0) + object[key];
    } 
    return sum;
  }, {});
}
```

## Solution №2
```javascript
const combine = (...args) =>
  args.reduce((pre, val) => (Object.keys(val).forEach(v => pre[v] = (pre[v] || 0) + val[v]), pre), {});
```
