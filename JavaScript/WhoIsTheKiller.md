# Who is the killer?


## Problem  

Some people have been killed!  
You have managed to narrow the suspects down to just a few. Luckily, you know every person who those suspects have seen on the day of the murders.  

Task.  
Given a dictionary with all the names of the suspects and everyone that they have seen on that day which may look like this:  

```javascript
{'James': ['Jacob', 'Bill', 'Lucas'],
 'Johnny': ['David', 'Kyle', 'Lucas'],
 'Peter': ['Lucy', 'Kyle']}
```
and also a list of the names of the dead people:  

```javascript
['Lucas', 'Bill']
```

return the name of the one killer, in our case 'James' because he is the only person that saw both 'Lucas' and 'Bill'


## Solution №1
```javascript
function killer(suspectInfo, dead) {
  for (let key in suspectInfo) {
    if (dead.every(person => suspectInfo[key].includes(person))) return key;
  }
}
```

## Solution №2
```javascript
function killer(suspectInfo, dead) {
 return Object.keys(suspectInfo).find(x => dead.every(y => suspectInfo[x].includes(y)))
}
```
