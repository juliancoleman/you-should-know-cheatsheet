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
```

### Formatting money

Let's suppose I passed you the number `3.1`. How would I get
it to read `$3.10`?

Note: JavaScript rounds to the nearest integer, leaving off
trailing zeros.

```js
const format = f64 => `$${f64.toFixed(2)}`;
```
