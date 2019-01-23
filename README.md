# you-should-know-cheatsheet
A cheatsheet of things you should know as a JS developer

## Simple Maths

### Filter odd numbers in array

Getting the odd numbers of an array is easy.

```js
const odds = arr =>
  arr.filter(v => v & 1);
```

### Filter even numbers in array

Getting evens is also easy!

```js
const evens = arr =>
  arr.filter(v => !(v & 1));
