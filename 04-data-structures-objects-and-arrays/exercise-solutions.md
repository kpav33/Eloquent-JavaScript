# The Sum of a Range

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

# Reversing an Array

## My Solution
```js
function reverseArray(array) {
  const reversedArr = [];
  for (let i = array.length - 1; i >= 0; i--) {
    reversedArr.push(array[i]);
  }
  return reversedArr;
}

function reverseArrayInPlace(array) {
  const reversedArr = [];
  let middle = Math.floor(array.length / 2);
  for (let i = 0; i < middle; i++) {
    let mirror = array[array.length - 1 - i];
    array[array.length - 1 - i] = array[i];
    array[i] = mirror;
  }
  return array;
}
```

## Author's solution
```js
function reverseArray(array) {
  let output = [];
  for (let i = array.length - 1; i >= 0; i--) {
    output.push(array[i]);
  }
  return output;
}

function reverseArrayInPlace(array) {
  for (let i = 0; i < Math.floor(array.length / 2); i++) {
    let old = array[i];
    array[i] = array[array.length - 1 - i];
    array[array.length - 1 - i] = old;
  }
  return array;
}
```

***

# A List

## My Solution
```js
function arrayToList(array) {
  let list = null;
  for (let i = array.length - 1; i >= 0; i--) {
    list = {value: array[i], rest: list}
  }
  return list;
}

function listToArray(obj) {
  const result = [];
  for (let node = obj; node; node = node.rest) {
    result.push(node.value);
  }
  return result;
}

function prepend(item, list) {
  let obj = {value: item, rest: list};
  return obj;
}

function nth(list, position) {
  let index = 0;
  for (let node = list; node; node = node.rest) {
    if (index === position) {
      return node.value;
    }
    index++;
  }
}

```

## Author's solution
```js
function arrayToList(array) {
  let list = null;
  for (let i = array.length - 1; i >= 0; i--) {
    list = {value: array[i], rest: list};
  }
  return list;
}

function listToArray(list) {
  let array = [];
  for (let node = list; node; node = node.rest) {
    array.push(node.value);
  }
  return array;
}

function prepend(value, list) {
  return {value, rest: list};
}

function nth(list, n) {
  if (!list) return undefined;
  else if (n == 0) return list.value;
  else return nth(list.rest, n - 1);
}
```

***

# Deep Comparison

## My Solution
```js
function deepEqual(obj1, obj2) {
  if (obj1 === obj2) {
    return true;
  }
  
  if (typeof obj1 === typeof obj2 && obj2 !== null && obj1 !== null) {
    let objKeys1 = Object.keys(obj1);
    let objKeys2 = Object.keys(obj2);
    
    if (objKeys1.length !== objKeys2.length) {
      return false;
    }
    for (let key of objKeys1) {
      if (!objKeys2.includes(key) || !deepEqual(obj1[key], obj2[key])) {
        return false;
      }
    }
    return true;
  }
}
```

## Author's solution
```js
function deepEqual(a, b) {
  if (a === b) return true;
  
  if (a == null || typeof a != "object" ||
      b == null || typeof b != "object") return false;

  let keysA = Object.keys(a), keysB = Object.keys(b);

  if (keysA.length != keysB.length) return false;

  for (let key of keysA) {
    if (!keysB.includes(key) || !deepEqual(a[key], b[key])) return false;
  }

  return true;
}
```