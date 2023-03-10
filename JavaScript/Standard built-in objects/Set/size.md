> Set

- Set 객체는 자료형에 관계 없이 원시 값과 객체 참조 모두 유일한 값을 저장한다. 즉, 중복을 제거할 수 있다

> Set.prototype.size

- size 접근자 속성은 Set 객체의 원소 수를 반환합니다.

```
const set1 = new Set();
const object1 = {};

set1.add(42);
set1.add('forty two');
set1.add('forty two');
set1.add(object1);

console.log(set1.size);
// Expected output: 3
```
