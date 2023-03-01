1. Math.floor()

- static method always rounds down and returns the largest integer less than or equal to a given number.

```
console.log(Math.floor(5.95));
// Expected output: 5

console.log(Math.floor(5.05));
// Expected output: 5

console.log(Math.floor(5));
// Expected output: 5

console.log(Math.floor(-5.05));
// Expected output: -6
```

2. Math.ceil()

- static method always rounds up and returns the smaller integer greater than or equal to a given number.

```
console.log(Math.ceil(.95));
// Expected output: 1

console.log(Math.ceil(4));
// Expected output: 4

console.log(Math.ceil(7.004));
// Expected output: 8

console.log(Math.ceil(-7.004));
// Expected output: -7
```

3. Math.round()

- static method returns the value of a number rounded to the nearest integer.

```
console.log(Math.round(0.9));
// Expected output: 1

console.log(Math.round(5.95), Math.round(5.5), Math.round(5.05));
// Expected output: 6 6 5

console.log(Math.round(-5.05), Math.round(-5.5), Math.round(-5.95));
// Expected output: -5 -5 -6

```
