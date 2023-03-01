1. Array.prototype.join()

- join() 메서드는 배열의 모든 요소를 연결해 하나의 문자열로 만듭니다.

```
const elements = ['Fire', 'Air', 'Water'];

console.log(elements.join());
// Expected output: "Fire,Air,Water"

console.log(elements.join(''));
// Expected output: "FireAirWater"

console.log(elements.join('-'));
// Expected output: "Fire-Air-Water"
```
