> Array.from()

- Array.from() 메서드는 유사 배열 객체(array-like object)나 반복 가능한 객체(iterable object)를 얕게 복사해 새로운Array 객체를 만듭니다.

```
console.log(Array.from('foo'));
// Expected output: Array ["f", "o", "o"]

console.log(Array.from([1, 2, 3], x => x + x));
// Expected output: Array [2, 4, 6]
```

- 1에서 N까지의 어레이 시퀀스를 만들기

```
// Array.from()
const N = 5;
const arr = Array.from({length: N}, (_, index) => index + 1);
console.log(arr); // [ 1, 2, 3, 4, 5 ]

// Array 생성자
const N = 5;
const arr = Array.from(Array(N), (_, index) => index + 1);

//
const N = 5;
const arr = Array.from(Array(N+1).keys()).slice(1);

// Spread 연산자
const N = 5;
const arr = [...Array(N+1).keys()].slice(1);

//
const N = 5;
const arr = [...Array(N).keys()].map(x => ++x);

//
const N = 5;
const arr = [...Array(N)].map((_, index) => index + 1);
```
