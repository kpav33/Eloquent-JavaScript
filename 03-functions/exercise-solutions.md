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