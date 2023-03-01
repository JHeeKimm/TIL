1. String.prototype.trim()

- trim() 메서드는 문자열 양 끝의 공백을 제거하고 원본 문자열을 수정하지 않고 새로운 문자열을 반환합니다. 여기서 말하는 공백이란 모든 공백문자(space, tab, NBSP 등)와 모든 개행문자(LF, CR 등)를 의미.
- 한쪽 끝의 공백만 제거한 새로운 문자열을 반환하려면 trimStart() 또는 trimEnd()를 사용.

```
const greeting = '   Hello world!   ';

console.log(greeting);
// Expected output: "   Hello world!   ";

console.log(greeting.trim());
// Expected output: "Hello world!";
```

2. String.prototype.split()

- split() 메서드는 String 객체를 지정한 구분자를 이용하여 여러 개의 문자열로 나눕니다.

```
const str = 'The quick brown fox jumps over the lazy dog.';

const words = str.split(' ');
console.log(words[3]);
// Expected output: "fox"

const chars = str.split('');
console.log(chars[8]);
// Expected output: "k"

const strCopy = str.split();
console.log(strCopy);
// Expected output: Array ["The quick brown fox jumps over the lazy dog."]
```

3. String.prototype.replace()

- replace() 메서드는 어떤 패턴에 일치하는 일부 또는 모든 부분이 교체된 새로운 문자열을 반환합니다. 그 패턴은 문자열이나 정규식(RegExp)이 될 수 있으며, 교체 문자열은 문자열이나 모든 매치에 대해서 호출된 함수일 수 있습니다.
- pattern이 문자열 인 경우, 첫 번째 문자열만 치환이 되며 원래 문자열은 변경되지 않습니다.

```
const p = 'The quick brown fox jumps over the lazy dog. If the dog reacted, was it really lazy?';

console.log(p.replace('dog', 'monkey'));
// Expected output: "The quick brown fox jumps over the lazy monkey. If the dog reacted, was it really lazy?"


const regex = /Dog/i;
console.log(p.replace(regex, 'ferret'));
// Expected output: "The quick brown fox jumps over the lazy ferret. If the dog reacted, was it really lazy?"
```

4. String.prototype.replaceAll()

- replaceAll() 메서드는 pattern의 모든 일치 항목이 replacement로 대체된 새 문자열을 반환합니다. pattern은 문자열 또는 RegExp일 수 있으며 replacement는 각 일치 항목에 대해 호출되는 문자열 또는 함수일 수 있습니다. 원래 문자열은 변경되지 않습니다.

```
const p = 'The quick brown fox jumps over the lazy dog. If the dog reacted, was it really lazy?';

console.log(p.replaceAll('dog', 'monkey'));
// Expected output: "The quick brown fox jumps over the lazy monkey. If the monkey reacted, was it really lazy?"


// Global flag required when calling replaceAll with regex
const regex = /Dog/ig;
console.log(p.replaceAll(regex, 'ferret'));
// Expected output: "The quick brown fox jumps over the lazy ferret. If the ferret reacted, was it really lazy?"
```
