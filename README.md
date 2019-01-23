# you-should-know-cheatsheet
A cheatsheet of things you should know as a JS developer

(examples in TS for type clarity)

## Arrays

### Filter odd numbers in array

Getting the odd numbers of an array is easy.

```ts
const odds = (arr: number[]) =>
  arr.filter(v => v & 1);
```

### Filter even numbers in array

Getting evens is also easy!

```ts
const evens = (arr: number[]) =>
  arr.filter(v => !(v & 1));
```

### Add an item to the beginning of the array

Unfortunately, `#unshift()` returns the new length of the
array, not the actual array.

[Array.prototype.unshift()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/unshift)

You could return the full array by wrapping in a closure:

```ts
function prepend(arr: any[], item: any) {
  arr.unshift(item);
  
  return arr;
}
```

Or even simpler with [spread](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax):

```ts
const newArr = [item, ...arr];
```

### Add an item to the end of the array

`#push()` also returns the new length of the array, not the
actual array.

[Array.prototype.push()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/push)

The above example works with this as well. Just replace
`unshift` with `push`.

Or, again, even simpler with [spread](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax):

```ts
const newArr = [...arr, item];
```

### Add an item anywhere in the array

Oddly returns an empty array if you add an item without
removing any items.

[Array.prototype.splice()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice)

You can insert (without removing items) with the following:

```ts
function insertAtIndex(arr: any[], val: any, index: number) {
  const deleteCount: number = 0;
  
  arr.splice(index, deleteCount, val);
  
  return arr;
}  
```

## Numbers

### Formatting money

Let's suppose I passed you the number `3.1`. How would I get
it to read `$3.10`?

Note: JavaScript rounds to the nearest integer, leaving off
trailing zeros.

```ts
const format = (f64: number): string => `$${f64.toFixed(2)}`;
```
