> Array.prototype.forEach()

- forEach() 메서드는 주어진 함수를 배열 요소 각각에 대해 실행한다.
- arr.forEach(callback(currentvalue[, index[, array]])[, thisArg])
- 주어진 callback을 배열에 있는 각 요소에 대해 오름차순으로 한 번씩 실행한다. 삭제했거나 초기화하지 않은 인덱스 속성에 대해서는 실행하지 않는다. (예: 희소 배열)
- forEach()로 처리할 요소의 범위는 최초 callback 호출 전에 설정된다. forEach() 호출을 시작한 뒤 배열에 추가한 요소는 callback이 방문하지 않는다. 배열의 기존 요소값이 바뀐 경우, callback에 전달하는 값은 forEach()가 요소를 방문한 시점의 값을 사용한다. 방문하기 전에 삭제한 요소는 방문하지 않는다.
- forEach()는 각 배열 요소에 대해 한 번씩 callback 함수를 실행한다. map()과 reduce()와는 달리 undefined를 반환하기 때문에 메서드 체인의 중간에 사용할 수 없다.(break, continue, return 구문을 사용해서 함수를 벗어날 수 없다.)
- forEach()는 배열을 변형하지 않는다. 그러나 callback이 변형할 수는 있다.
- 예외를 던지지 않고는 forEach()를 중간에 멈출 수 없다.

```
const array1 = ['a', 'b', 'c'];

array1.forEach(element => console.log(element));

// Expected output: "a"
// Expected output: "b"
// Expected output: "c"
```

> forEach와 map 메소드

- 공통점: 첫번째로 콜백함수를 인자로 받고 그 함수의 인자는 (배열 원소 값,그 값의 인덱스,배열 자체)

- 차이점
  - forEach : return 값이 없다
  - map : return 값이 있다

```
let data= [1, 2, 3, 4, 5]
// forEach 를 사용해서 원소의 값들을 각각 3씩 증가시키기
let result = [];
data.forEach(x => { result.push(x + 3) });
console.log(result);

// map 을 사용해서 원소의 값들을 각각 3씩 증가시키기
let result2 = data.map(x => { return x + 3});
console.log(result2);
```
