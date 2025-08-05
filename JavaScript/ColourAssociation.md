# Colour Association

## Problem
Colour plays an important role in our lifes. Most of us like this colour better then another. User experience specialists believe that certain colours have certain psychological meanings for us.

You are given a 2D array, composed of a colour and its 'common' association in each array element. The function you will write needs to return the colour as 'key' and association as its 'value'.

For example:
```javascript
var array = [["white", "goodness"], ...] //returns [{white: 'goodness'}, ...]
```

## Solution №1
```javascript
function colourAssociation(array){
  let colourObjectArray = [];
  for (let i = 0; i < array.length; i++) {
    let colourObject = {};
    let key = array[i][0];
    let value = array[i][1];
    colourObject[key] = value;
    colourObjectArray.push(colourObject);
  }
  return colourObjectArray;
}
```

## Solution №2
```javascript
const colourAssociation = array =>
  array.map(([colour, association]) => ({[colour]:association}))
```

## Solution №3
```javascript
function colourAssociation(array){
  return array.map(x => ({ [x[0]]: x[1]}));
}
```
