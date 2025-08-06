# Whose bicycle?

## Problem
I am the father of three wonderful sons. before the beginning of the school year, I promised them that I would buy a bicycle for someone who would bring the best marks at the end of the school year. it's time to keep promises and I count on you.

You have 3 input objects(school diaries) with school subjects and marks (1-10). For example:

```javascript
{
  'algebra': 6,
  'history': 8,
  'physics': 9,
  'geography': 2,
  'chemistry': 9
}
```

Return please :

```javascript
'I need to buy a bicycle for my first son.' // the sum of the marks is the highest  in the first diary.

'I need to buy a bicycle for my second son.' // the sum of the marks is the highest in the second diary.

'I need to buy a bicycle for my third son.' //  the sum of the marks is the highest in the third diary.
```

If two or three sons have the same highest marks, you need to choose the younger one. 


## Solution №1
```javascript
function whoseBicycle(diary1, diary2, diary3) {
  let diaries = [diary1, diary2, diary3];
  let sumOfMarks = diaries.map(diary => {
    let sum = 0;
    for (let key in diary){
      sum += diary[key];
    }
    return sum;
  });
  
  let index = sumOfMarks.lastIndexOf(Math.max(...sumOfMarks));
  
  const names = ["first", "second", "third"];

  return `I need to buy a bicycle for my ${names[index]} son.`;

}
```

## Solution №2
```javascript
function whoseBicycle(a, b, c) {
  [a, b, c] = [a, b, c].map(x => Object.values(x).reduce((y, z) => y + z, 0));
  let n = Math.max(a, b, c);
  return `I need to buy a bicycle for my ${n === c ? "third" : n === b ? "second" : "first"} son.`;
}
```

## Solution №3
```javascript
function whoseBicycle(dairy1, dairy2, dairy3) {
  const diaries = [dairy1, dairy2, dairy3];
  const son = {
    0: 'first',
    1: 'second',
    2: 'third'
  };
  const scores = diaries.map((diary, index) => {
    const keys = Object.keys(diary);
    
    return keys.reduce((acc, cur) => acc + diary[cur], 0);
  });
  
  const maxValue = Math.max(...scores);
  
  const maxDiary = scores.lastIndexOf(maxValue);
  
  return `I need to buy a bicycle for my ${son[maxDiary]} son.`;
}
```
