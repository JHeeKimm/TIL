> Variable

1. Use strict  
   ECMAScript5  
   바닐라 js일 때, 선언함으로써 조금 더 상식적인 범위안에서 js를 사용하게 해줌  
   "use strict";

2. Variable, rw(reade/write)

- let (added in ES6) : mutable

- var (don't ever use this!)
  var hoisting : 어디에 선언했냐와 상관없이 항상 제일 위로 선언을 끌어올려주는 것
  has no block scope

3. Constant, r(read only) : 한 번 할당한 뒤 변경될 수 없음

- Immutable data types: premitive types, frozen objects (i.e. object.freeze())
- Mutable data types: all objects by default are mutable in JS
- favor immutable data type always for a few reasons:
  - security
  - thread safety
  - reduce human mistakes

4. Variable types

- primitive, single item : number, string, boolean, null, undefined, symbol
- object, box container : data structure
- function, first-class function

Number : Infinity, -Infinity, NaN, bigInt(~n)  
String : ..., template literals(``벡틱사용)  
Boolean

- false: 0, null, undefined, NaN, ''
- true: any other value

Symbol : 고유한 식별자가 필요할 때 사용

5. Dynamic typing : dynamically typed language  
   런타임에서 타입이 결정되기 때문에 할당한 값에 따라 타입이 변경될 수 있음
