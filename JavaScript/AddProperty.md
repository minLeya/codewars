# Add property to every object in array

## Problem
Your task is to add a new property usersAnswer to every object in the array questions. The value of usersAnswer should be set to null. The solution should work for array of any length.

The questions array is already defined for you and is not the same as the one in the example.

## Solution №1
```javascript
questions.forEach(function (i) {
        i.usersAnswer = null;
    });
```

## Solution №2
```javascript
questions.forEach(x => x.usersAnswer = null);
```

## Solution №3
```javascript
for (obj of questions) {
  obj['usersAnswer'] = null;
}
```

## Solution №4
```javascript
function addProperty(questions) {
  questions.forEach(q => q.usersAnswer = null);
}

addProperty(questions);
```
