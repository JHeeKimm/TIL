> for...in

- for...in문은 상속된 열거 가능한 속성들을 포함하여 객체에서 문자열로 키가 지정된 모든 열거 가능한 속성에 대해 반복함.
- 열거 가능한 non-Symbol 속성에 대해서만 반복 (Symbol로 키가 지정된 속성은 무시)
- 객체 자체의 모든 열거 가능한 속성들과 프로토타입 체인으로부터 상속받은 속성들에 대해 반복
- for...in은 인덱스의 순서가 중요한 Array에서 반복을 위해 사용할 수 없다.(특정 순서에 따라 인덱스를 반환하는 것을 보장할 수 없다. 정수가 아닌 이름을 가진 속성, 상속된 모든 열거 가능한 속성들을 반환한다.)
- 객체의 속성을 확인(콘솔이나 다른 방법으로 출력)할 수 있기 때문에 실질적으로 디버깅을 위해 사용
- 키-값 쌍이 선호되는 데이터의 경우(속성이 "key"의 역할을 함) 특정 값을 가진 키가 있는지 확인하려는 경우에 for...in을 사용

```
// 열거 가능한 non-Symbol속성들을 반복해서 속성의 이름과 그 값을 기록
const obj = {a: 1, b: 2, c: 3};

for (const prop in obj) {
  console.log(`obj.${prop} = ${obj[prop]}`);
}

// Output:
// "obj.a = 1"
// "obj.b = 2"
// "obj.c = 3"

```