- 'a'는 97번이고, 'z'는 122번

> String.prototype.charCodeAt()

- charCodeAt() 메서드는 주어진 인덱스에 대한 UTF-16 코드를 나타내는 0부터 65535 사이의 정수를 반환한다.
- str.charCodeAt(index)

```
'ABC'.charCodeAt(0); // returns 65
```

> String.fromCharCode()

- fromCharCode() 메서드는 UTF-16 코드 유닛의 시퀀스로부터 문자열을 생성해 반환한다.
- String.fromCharCode(num1[, ...[, numN]])

```
String.fromCharCode(65, 66, 67);  // "ABC"
String.fromCharCode(0x2014)       // "—"
String.fromCharCode(0x12014)      // 숫자 '1'은 무시해서 "—"
```
