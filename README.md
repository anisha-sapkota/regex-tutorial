# Rest and Spread Operators

JavaScript uses `...` for both `rest` and `spread` operators but they work differently. In this tutorial we will look at when and how to use these two operators.

## Rest Operator

Ever wondered how the `Math.max()` function is able to take indefinite numbers of arguments and how you could do the same?

Behold the `rest` operator!

The `rest` operator allows a function to accept `n` number of arguments by converting them into an array.

Suppose you want to write a function that returns the sum of numbers but you don't know how many numbers the function will receive as parameters. You can use the rest operator - `...`.

### Example

In the following example, the sum function takes indefinite number of arguments and returns their sum.

```javascript
const sum = (...numbers) => {
  let total = 0;
  for (const number of numbers) {
    total += number;
  }
  return total;
};

console.log(sum(1, 2, 3));
// output: 6

console.log(sum(1, 2, 3, 4, 5, 6, 7, 8, 9));
// output: 45
```

When defining a function with rest parameters, the `...` must always be used last.

```javascript
const myFunction = (x, ...rest, y) => {
  // this will throw error
  // y after rest doesn't make sense
}
```

## Spread Operator

Sometimes we need to do exactly the opposite of `rest` operator. Given an array of elements, expand them into individual elements.

Suppose you have an array of numbers and would like to call the `Math.max()` function but the function doesn't accept an array and requires you to pass them as individual numbers. This is the perfect use case for the spread operator.

```javascript
const myNumbers = [20, 68, 78, 21, 99];

console.log(Math.max(...myNumbers));
// outputs: 99
```

There are various other use cases for the spread operator:

### Copy an array

The spread operator makes it easy to copy an array.

```javascript
const arr1 = [1, 2, 3, 4, 5];

const arr2 = [...arr1, 6, 7, 8, 9];
```

### Concatenate arrays

It can also be used to concatenate arrays.

```javascript
const arr1 = [1, 2, 3, 4, 5];
const arr2 = [6, 7, 8, 9];

const combined = [...arr1, ...arr2];
```

The spread operator also works with objects. It can be used to copy properties of one object into a new object.

```javascript
const obj1 = {
  color: "red",
};

const obj2 = {
  ...obj1,
  shape: "square",
};
```
