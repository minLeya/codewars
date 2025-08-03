# Merge two sorted arrays into one

## Problem
You are given two sorted arrays that contain only integers. These arrays may be sorted in either ascending or descending order. Your task is to merge them into a single array, ensuring that:

The resulting array is sorted in ascending order.

Any duplicate values are removed, so each integer appears only once.

If both input arrays are empty, return an empty array.

No input validation is needed, as both arrays are guaranteed to contain zero or more integers.

## Solution №1
```javascript
function mergeArrays(arr1, arr2) {
  let newArr = arr1.concat(arr2).sort((a, b) => a - b);
  return newArr.filter((item, index) => newArr.indexOf(item) === index);
  // filter перебирает каждый элемент массива и выполняет передаваемую функцию
  // стрелочная функция внутри filter
  // если индекс первого вхождения (indexOf) совпадает с индексом (местоположением) в массиве - все норм
  // если индекс первого вхождения не совпадает с местоположением в массиве - убирается фильтром
}
```

## Solution №2
```javascript
function mergeArrays(arr1, arr2) {
  return Array.from(new Set(arr1.concat(arr2).sort((a,b) => (a-b))));
}
```
