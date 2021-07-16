# Flattening

## My Solution
```js
let arrays = [[1, 2, 3], [4, 5], [6]];
function flatten(arr) {
  return arr.reduce((flat, toFlatten) => {
    return flat.concat(Array.isArray(toFlatten) ? flatten(toFlatten) : toFlatten);
  }, []);
}
console.log(flatten(arrays));
```

## Author's solution
```js
let arrays = [[1, 2, 3], [4, 5], [6]];
console.log(arrays.reduce((flat, current) => flat.concat(current), []));
```
***

# Your Own Loop

## My Solution
```js
function loop(value, test, update, body) {
  for (let i = value; test(i); i = update(i)) {
    body(i);
  }
}
loop(3, n => n > 0, n => n - 1, console.log);
```

## Author's solution
```js
function loop(start, test, update, body) {
  for (let value = start; test(value); value = update(value)) {
    body(value);
  }
}
loop(3, n => n > 0, n => n - 1, console.log);
```
***

# Everything

## My Solution
```js
// Loop version
function every(array, test) {
  // Your code here.
  for (let i = 0; i < array.length; i++) {
    if (!test(array[i])) return false;
  }
  return true;
}

// Version with the some method
function everySome(array, test) {
  return !array.some(num => {
    return !test(num);
  });
}

console.log(every([1, 3, 5], n => n < 10));
// → true
console.log(every([2, 4, 16], n => n < 10));
// → false
console.log(every([], n => n < 10));
// → true
```

## Author's solution
```js
function every(array, predicate) {
  for (let element of array) {
    if (!predicate(element)) return false;
  }
  return true;
}

function every2(array, predicate) {
  return !array.some(element => !predicate(element));
}

console.log(every([1, 3, 5], n => n < 10));
// → true
console.log(every([2, 4, 16], n => n < 10));
// → false
console.log(every([], n => n < 10));
// → true
```
***

# Dominant Writing Direction

## My Solution
```js
function dominantDirection(text) {
  // Your code here.
  let scripts = countBy(text, char => {
    let script = characterScript(char.codePointAt(0));
    return script ? script.direction : "none";
  }).filter(({name}) => name != "none");
  
  let count;
  let direction;
  scripts.map(obj => {
    count = obj.count;
    direction = obj.name;
    if (obj.count > count) {
      count = obj.count;
      direction = obj.name;
    };
  });
  return direction;
}

console.log(dominantDirection("Hello!"));
// → ltr
console.log(dominantDirection("Hey, مساء الخير"));
// → rtl
```

## Author's solution
```js
function dominantDirection(text) {
  let counted = countBy(text, char => {
    let script = characterScript(char.codePointAt(0));
    return script ? script.direction : "none";
  }).filter(({name}) => name != "none");

  if (counted.length == 0) return "ltr";

  return counted.reduce((a, b) => a.count > b.count ? a : b).name;
}

console.log(dominantDirection("Hello!"));
// → ltr
console.log(dominantDirection("Hey, مساء الخير"));
// → rtl
```