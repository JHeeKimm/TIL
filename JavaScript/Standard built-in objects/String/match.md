> String.prototype.match()

- match() 메서드는 문자열이 정규식과 매치되는 부분을 검색한다.
- str.match(regexp or 문자열)
- 문자열이 정규식과 일치하면, 일치하는 전체 문자열을 첫 번째 요소로 포함하는 Array를 반환한 다음 괄호 안에 캡처된 결과가 온다. 일치하는 것이 없으면 null이 반환된다.
- match()와 함께 글로벌(g) 및 대/소문자 무시(i) 플래그 사용하기

```
const str = 'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz';
const regexp = /[A-E]/gi;
const matches_array = str.match(regexp);

console.log(matches_array);
// ['A', 'B', 'C', 'D', 'E', 'a', 'b', 'c', 'd', 'e']
```
