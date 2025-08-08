# Minimize Sum Of Array (Array Series #1)


## Problem
vowelOne
Write a function that takes a string and outputs a strings of 1's and 0's where vowels become 1's and non-vowels become 0's.

All non-vowels including non alpha characters (spaces,commas etc.) should be included.

Examples:
```javascript
vowelOne( "abceios" ) // "1001110"

vowelOne( "aeiou, abc" ) // "1111100100"
```  

## Solution №1
```javascript
function vowelOne(s){
  let vowel = "aeiou".split('');
  let arr = s.toLowerCase().split('');
  let result = arr.map(char => {
    return vowel.includes(char) ? 1 : 0;
  })
  return result.join('');
}
```

## Solution №2
```javascript
function vowelOne(s){
  return s.split('').map(x => ('aeiouAEIOU'.includes(x)) ? 1 : 0).join('');
}
```
