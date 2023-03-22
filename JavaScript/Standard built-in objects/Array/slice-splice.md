> Array.prototype.slice()

- slice() 메서드는 어떤 배열의 begin 부터 end 까지(end 미포함)에 대한 얕은 복사본을 새로운 배열 객체로 반환한다. 원본 배열은 바뀌지 않는다.
- arr.slice([begin[, end]])
- begin: Optional
  - 0을 시작으로 하는 추출 시작점에 대한 인덱스, 음수 인덱스는 배열의 끝에서부터의 길이를 나타낸다.
  - slice(-2) 는 배열에서 마지막 두 개의 엘리먼트를 추출한다.
  - begin이 undefined인 경우에는, 0번 인덱스부터 slice 한다.
  - begin이 배열의 길이보다 큰 경우에는, 빈 배열을 반환한다.
- end: Optional
  - 추출을 종료 할 0 기준 인덱스, slice 는 end 인덱스를 제외하고 추출한다.
  - end가 생략되면 slice()는 배열의 끝까지(arr.length) 추출한다.
  - 만약 end 값이 배열의 길이보다 크다면, slice()는 배열의 끝까지(arr.length) 추출한다.
  - 예를들어 slice(2,-1) 는 세번째부터 끝에서 두번째 요소까지 추출한다.

```
const animals = ['ant', 'bison', 'camel', 'duck', 'elephant'];

console.log(animals.slice(2));
// Expected output: Array ["camel", "duck", "elephant"]

console.log(animals.slice(2, 4));
// Expected output: Array ["camel", "duck"]

console.log(animals.slice(1, 5));
// Expected output: Array ["bison", "camel", "duck", "elephant"]

console.log(animals.slice(-2));
// Expected output: Array ["duck", "elephant"]

console.log(animals.slice(2, -1));
// Expected output: Array ["camel", "duck"]

console.log(animals.slice());
// Expected output: Array ["ant", "bison", "camel", "duck", "elephant"]

```

> Array.prototype.splice()

- splice() 메서드는 배열의 기존 요소를 삭제 또는 교체하거나 새 요소를 추가하여 배열의 내용을 변경한다.
- array.splice(start[, deleteCount[, item1[, item2[, ...]]]])
- start:
  - 배열의 변경을 시작할 인덱스
  - 배열의 길이보다 큰 값이라면 실제 시작 인덱스는 배열의 길이로 설정된다.
  - 음수인 경우 배열의 끝에서부터 요소를 세어나간다(원점 -1, 즉 -n이면 요소 끝의 n번째 요소를 가리키며 array.length - n번째 인덱스와 같음).
- deleteCount: Optional
  - 배열에서 제거할 요소의 수
  - deleteCount를 생략하거나 값이 array.length - start보다 크면 start부터의 모든 요소를 제거한다.
  - deleteCount가 0 이하라면 어떤 요소도 제거하지 않는다. 이 때는 최소한 하나의 새로운 요소를 지정해야 한다.
- item1, item2, <em>...</em>: Optional
  - 배열에 추가할 요소
  - 아무 요소도 지정하지 않으면 splice()는 요소를 제거하기만 한다.

```
const months = ['Jan', 'March', 'April', 'June'];
months.splice(1, 0, 'Feb');
// Inserts at index 1
console.log(months);
// Expected output: Array ["Jan", "Feb", "March", "April", "June"]

months.splice(4, 1, 'May');
// Replaces 1 element at index 4
console.log(months);
// Expected output: Array ["Jan", "Feb", "March", "April", "May"]

```
