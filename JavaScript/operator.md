> Operator

1. String concatenation

- ''+''
- ''+num
- `string literals: 1+2=${1+2}`

2. Numeric operators

- add +
- substract -
- divide /
- multiply \*
- remainder %
- exponentiation \*\*

3. Increment and decrement operators

- preIncrement : ++counter, 1증가 후 할당
- postIncrement : counter++, 할당 후 1증가

4. Assignment operators

- x += y; x = x + y
- -=
- \*=
- /=

5. Comparison operators

- <, <=, >, >=

6. Logical operators

- || or : 간단한 조건부터 작성, 무거운 조건은 뒤에
- && and
- ! not

7. Equality

- ==,!= : loose equality, with type conversion
- ===, !== : strict equality, no type conversion

  0 == false; true  
   0 === false; false  
   '' == false; true  
   '' === false' false  
   null == undefined; true  
   null === undefined; false

8. Conditional operators: if

- if, else if, else

9. Ternary operator: ?

- condition ? value1 : value2;
- 간단할 때만 사용

10. Switch statement

- use for multiple if checks
- use for enum-like value check
- use for multiple type checks in TS

11. Loops

- while loop, while the condition is truthy, body code is executed.
- do while loop, body code is executed first, then check the condition.
- for loop, for(begin; condition; step)
- inline variable declaration : 블럭 안에 지역변수 선언  
  for(let i=3; i>0; i=i-2){ }
- nested loops : for문안에 for문
- break, continue
