# Looping a Triangle

## My Solution
```js
let hash = "#";
for (let i = 1; i < 8; i++) {
  console.log(hash.repeat(i));
}
```

## Author's solution
```js
for (let i = "#"; i.length < 8; i += "#") {
  console.log(i);
}
```
***

# FizzBuzz

## My Solution
```js
for (let i = 0; i < 101; i++) {
  if (i % 15 === 0) {
    console.log("FizzBuzz");
  } else if (i % 3 === 0) {
    console.log("Fizz");
  } else if (i % 5 === 0) {
    console.log("Buzz");
  } else {
    console.log(i);
  }
}
```

## Author's solution
```js
for (let i = 0; i < 101; i++) {
  let output = "";
  if (i % 3 === 0) output += "Fizz";
  if (i % 5 === 0) output += "Buzz";
  console.log(output || i);
}
```
***

# ChessBoard

## My Solution
```js
let chessBoard = "";
let hash = " #";
let hash1 = "# ";
let size = 8;

for (let i = 0; i < size; i++) {
  if (i % 2 === 0) {
    if (Number.isInteger(size / 2)) {
      chessBoard += `${hash.repeat(size / 2)}\n`;
    } else {
      chessBoard += `${hash.repeat(size / 2)} \n`;
    }
  } else {
    if (Number.isInteger(size / 2)) {
      chessBoard += `${hash1.repeat(size / 2)}\n`;
    } else {
      chessBoard += `${hash1.repeat(size / 2)}#\n`;
    }
  }
}

console.log(chessBoard);
```

## Author's solution
```js
let size = 8;
let board = "";

for (let y = 0; y < size; y++) {
  for (let x = 0; x < size; x++) {
    if ((x + y) % 2 == 0) {
      board += " ";
    } else {
      board += "#";
    }
  }
  board += "\n";
}

console.log(board);
```