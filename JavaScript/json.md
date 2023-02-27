> JSON

- HTTP : Hypertext Transfer Protocal, client와 server가 어떻게 통신할 수 있는지 정의한 것. request/response
- AJAX : Asynchronous JavaScript And XML, 웹페이지에서 동적으로 서버에게 데이터를 주고 받을 수 있는 기술. (XHR(XMLHttpRequest) 오브젝트, fetch()API, JSON, XML)
- JSON
  - JavaScript Object Notation
  - ECMAScript3
  - Object{key: value}
  - 브라우저, 모바일/서버 데이터 주고 받을 때
  - 서버와 통신을 하지 않고 object를 파일 시스템에 저장할 때
  - simplest data interchange format 데이터를 주고 받을 때 쓸 수 있는 가장 간단한 파일 포맷
  - lightweight text-based structure 텍스트 기반으로 한 가볍고
  - easy to read
  - key-value pairs 키와 밸류로 이루어진 파일 포맷
  - used for serialization and transmission of data between the network the network connection 데이터를 서버와 주고 받을 때, 직렬화 하고 데이터를 전송할 때 사용
  - independent programming language and platform 프로그래밍 언어와 플랫폼에 상관 없이 사용 가능
  - Overloading : 동일한 이름의 함수가 어떤 파라미터를 전달하느냐, 몇개의 파라미터를 전달하냐에 따라 각각 다른 방식으로 호출이 가능함.

==> object --serialize--> string , object <--deserialize-- string

1. Object to JSON

- stringify(obj)

```
let json = JSON.stringify(true);
console.log(json); // true

json = JSON.stringify(['apple', 'banana']);
console.log(json); // ["apple", "banana"]

const rabbit = {
    name: 'tori',
    color: 'white',
    size: null,
    birthDate: new Date(),
    jump: () => {
        console.log(`${name} can jump!`);
    },
};

// 오브젝트를 스트링화해서 제이슨으로 만듦
// 함수는 오브젝트에 있는 데이터가 아니기 때문에 jump함수는 제외됨. js에 있는 특별한 데이터 symbol도 json에 포함되지 않음
json = JSON.stringify(rabbit);
console.log(json);

json = JSON.stringify(rabbit, ['name', 'color']); // 원하는 프로퍼티만 정의를 하면, 해당하는 프로퍼티만 json으로 변환됨
console.log(json);

// 좀 더 세밀하게 통제하고 싶을 때, 콜백함수를 사용함
json = JSON.stringify(rabbit, (key, value) => {
    console.log(`key: ${key}, value: ${value}`);
    return key === 'name' ? 'ellie' : value;
});
console.log(json);
```

2. JSON to Object

- parse(json)

```
json = JSON.stringify(rabbit);
console.log(json);
// string된걸 obj에 넣었으니 getDate() 쓰려면 새로 담아줘야함
const obj = JSON.parse(json, (key, value) => {
    console.log(`key: ${key}, value: ${value}`);
    return key === 'birthDate' ? new Date(value) : value;
});
console.log(obj);

rabbit.jump(); // can jump!
// obj.jump();  // error. rabbit을 json으로 만들었을 때 함수를 제외한 데이터들만 담겼으니깐, 그 데이터를 새로 오브젝트로 만들었으니 jump함수는 없음.

console.log(rabbit.birthDate.getDate());
console.log(obj.birthDate.getDate());
```

> JSON에 대해 조금더 공부를 하고 싶으면

- MDN ➡️ https://developer.mozilla.org/en-US/d...
- JavaScript.info ➡️ https://javascript.info/json
- JavaScript.info 한국어 ➡️ https://ko.javascript.info/json

> 유용한 사이트

- JSON Diff checker(서버에서 받아온 데이터가 첫번째와 두번째가 어떻게 다른지 모를 때): http://www.jsondiff.com/
- JSON Beautifier/editor(망가진 포맷 예쁘게): https://jsonbeautifier.org/
- JSON Parser(json으로부터 object가 어떻게 표기되는지 확인 가능): https://jsonparser.org/
- JSON Validator(json이 이상할 때 확인용도): https://tools.learningcontainer.com/j...
