> Function

- fundamental building block in the program
- subprogram can be used multiple times
- performs a task or calculates a value

1. Function declaration

- function name(param1, param2){ body... return;}
- one function === one thing
- naming: doSometing, command, verb
- function is object in JS

2. Parameters

- primitive parameters: passed by value
- object parameters: passed by reference

3. Default parameters (added in ES6)

```
   function showMessage(message, **_from='unknown'_**){
    console.log(`${message} by ${from}`);
    }
    showMessage('Hi!')
    ==> Hi! by unknown
```

4. Rest parameters (added in ES6)  
   인자를 배열로 담아냄

```
   function printAll(**_...args_**){
   //
   for(let i=0; i<args.length; i++){
   console.log(args[i]);
   }
   //
   for(const arg **of** args){
   console.log(arg);
   }
   //
   args.forEach((arg)=>console.log(arg));
   printAll('dream', 'coding', 'ellie');
   ===> dream
   coding
   ellie
```

5. Local scope

- 지역변수, 블록안에서 선언된 변수
- 밖에서는 안이 보이지 않고, 안에서만 밖을 볼 수 있다.

6. Return a value
7. Early return, early exit

- 조건이 맞지 않을 때, 빨리 리턴한 다음 필요한 긴 로직 작성

> First-class function

- 다른 변수와 같이 변수에 할당되고, 함수에 매개변수로 전달되고, 리턴값으로도 리턴이 된다.

1. Function expression

- a function declaration can be called earlier than it is defined.(hoisted) 함수 선언식
- a function expression is created when the execution reaches it. 함수 표현식
  // anonymous function
  const print = function (){}
  print();

2. Callback function using function expression

```

function randomQuiz(answer, printYes, printNo){
if(answer === 'love you'){
printYes();
} else{
printNo();
}
}
// anonymous function
const printYes = function(){
console.log('yes!')
}
// named function
// better debugging in debugger's stack traces
// recursions(함수 안에서 함수 자신을 호출할 때, 정말 필요할 때만 사용)
const printNo = function print(){
console.log('no!')
}
randomQuiz('wrong', printYes, printNo) ==>no!
randomQuiz('love you', printYes, printNo) ==>yes!

```

// Arrow function
// always anonymous

```

const simplePrint = function (){
console.log('simplePrint!');
};
const simplePrint = () => console.log('simplePrint!');

```

// IIFE : Immediately Invoked Function Expression 선언함과 동시에 호출

```

**_(_** function hello() {
console.log('IIFE');
}**_)_** **_()_**

```

> Quiz

```

function calculate(command, a, b) {
switch (command) {
case "add":
return a + b;
case "substract":
return a - b;
case "divide":
return a / b;
case "multiply":
return a \* b;
case "remainder":
return a % b;
default:
throw Error("unknown command");
}
}
console.log(calculate("add", 2, 3));

```
