> String.prototype.search()

- search() 메서드는 정규 표현식과 이 String 객체간에 같은 것을 찾기 위한 검색을 실행한다.
- str.search(regexp or 문자열)
- 정규표현식과 주어진 스트링간에 첫번째로 매치되는 것의 인덱스를 반환한다. 찾지 못하면 -1 를 반환한다.

```
const str = "hey JudE";
const re = /[A-Z]/g;
const re2 = /[.]/g;
console.log(str.search(re)); // returns 4, which is the index of the first capital letter "J"
console.log(str.search(re2)); // returns -1 cannot find '.' dot punctuation
```
