# Minimum

## My Solution
```js
function range(start, end, step = 1) {
    const result = [];
    if (step < 0) {
        for (let i = start; i >= end; i -= Math.abs(step)) {
            result.push(i);
        }
    } else {
        for (let i = start; i <= end; i += step) {
            result.push(i);
        }
    }
    return result;
}

function sum(array) {
    return array.reduce((a, b) => a + b, 0);
}
```

## Author's solution
```js
function range(start, end, step = start < end ? 1 : -1) {
  let array = [];

  if (step > 0) {
    for (let i = start; i <= end; i += step) array.push(i);
  } else {
    for (let i = start; i >= end; i += step) array.push(i);
  }
  return array;
}

function sum(array) {
  let total = 0;
  for (let value of array) {
    total += value;
  }
  return total;
}
```
***

# Recursion

## My Solution

## Author's solution

***

# Bean Counting

## My Solution

## Author's solution
