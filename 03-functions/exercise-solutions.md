# Minimum

## My Solution
```js
function min(a, b) {
  if (a < b) return a;
  else return b; 
}
```

## Author's solution
```js
function min(a, b) {
  if (a < b) return a;
  else return b;
}
```
***

# Recursion

## My Solution
```js
function isEven(num) {
  if (num === 0) return true;
  else if (num === 1) return false;
  else if (num < 0) return isEven(Math.abs(num));
  else return isEven(num - 2);
}
```

## Author's solution
```js
function isEven(n) {
  if (n == 0) return true;
  else if (n == 1) return false;
  else if (n < 0) return isEven(-n);
  else return isEven(n - 2);
}
```
***

# Bean Counting

## My Solution
```js
/*
function countBs(string) {
  let count = 0;
  for (let i = 0; i < string.length; i++) {
    if (string[i] === "B") count++;
  }
  return count;
}
*/

function countChar(string, char) {
  let count = 0;
  for (let i = 0; i < string.length; i++) {
    if (string[i] === char) count++;
  }
  return count;
}

// Rewrite countBs with countChar
function countBs(string) {
  return countChar(string, "B");
}

```

## Author's solution
```js
function countChar(string, ch) {
  let counted = 0;
  for (let i = 0; i < string.length; i++) {
    if (string[i] == ch) {
      counted += 1;
    }
  }
  return counted;
}

function countBs(string) {
  return countChar(string, "B");
}
```