> Callback

- JavaScript is synchronous.동기적, 순서대로
- Execute the code block by order after hoisting. 호이스팅이 된 이후부터, 코드의 순서에 맞춰서 하나하나씩 동기적으로 실행된다.
- hoisting : var, function declaration 함수 선언들이 제일 위로 올라가는 것

```
console.log('1');
setTimeout(() => console.log('2'), 1000); // asynchronous 비동기방법
console.log('3');
```

1. Synchronous callback

```
function printImmediately(print){
    print();
}
printImmediately(() => console.log('hello'));
```

2. Asynchronous callback

```
function printWithDelay(print, timeout){
    setTimeout(print, timeout);
}
printWithDelay(() => console.log('async callback'), 2000);
```

3. Callback Hell example

- 가독성이 떨어짐
- 디버깅하고 문제 분석 어려움
- 유지보수 어려움

```
class UserStorage{
    loginUser(id, password, onSuccess, onError){
        setTimeout(() => {
            if(
                (id === 'ellie' && password === 'dream') ||
                (id === 'coder' && password === 'academy')
            ){
                onSuccess(id);
            } else{
                onError(new Error('not found'));
            }
        }, 2000);
    }

    getRoles(user, onSuccess, onError){
        setTimeout(() => {
            if(user === 'ellie'){
                onSuccess({name: 'ellie', role: 'admin'});
            }else{
                onError(new Error('no access'));
            }
        }, 1000);
    }
}

const userStorage = new UserStorage();
const id = prompt('enter your id');
const password = prompt('enter your password');
userStorage.loginUser(
    id,
    password,
    (user) => {
        userStorage.getRoles(
            user,
            (userWithRoles) => {
                alert(`Hello ${userWithRoles.name}, you have a ${userWithRoles.role} role`)
            },
            (error) => {console.log(error)}
        );
    },
    (error) => {console.log(error)});
```
