> Promise

- Primise is a JavaScript object for asynchronous operation. JS에서 제공하는 비동기를 간편하게 처리할 수 있게 하는 object.
- State: pending -> fulfilled state or rejected state 기능을 성공했는지, 실패했는지
- Producer vs Consumer

1. Producer

- when new Promise is create, the executor runs automatically.
- 사용자가 요구했을 때만 network 요청을 해야한다면 불필요한 네트워크 통신이 일어날 수 있기 때문에 콜백함수가 바로 실행되는 것을 유의하여 작성해야한다.

```
const promise = new Promise((resolve, reject) => {
    // doing some heavy work (network, read files)
    console.log('doing something...');
    setTimeout(() => {
       // resolve('ellie');
        reject(new Error('no network'));
    }, 2000);
});

```

2. Consumers: then, catch, finally

- then : promise가 정상적으로 잘 수행이 되어서, resolve 콜백함수를 통해서 전달한 값이 파라미터 value로 전달됨.
- catch : 실패한 경우
- finally : 성공과 실패와 상관없이 어떤 기능을 마지막으로 사용하고 싶을 때.

```
promise
    .then(value => {
        console.log(value);
    })
    .catch(error => {
        console.log(error);
    })
    .finally(() => {
        console.log('finally')
    });
```

3. Promise chaining

```
const fetchNumber = new Promise((resolve, reject) => {
    setTimeout(() => resolve(1), 1000);
});

fetchNumber
    .then(num => num * 2)
    .then(num => num * 3)
    .then(num => {
        return new Promise((resolve, reject) => {
            setTimeout(() => resolve(num - 1), 1000);
        });
    })
    .then(num => console.log(num));
```

4. Error Handling

```
const getHen = () =>
    new Promise((resolve, reject) => {
        setTimeout(() => resolve('🍗'), 1000);
    });
const getEgg = hen =>
    new Promise((resolve, reject) => {
        setTimeout(() => reject(new Error(`error! ${hen} => 🥚`)), 1000);
    });
const cook = egg =>
    new Promise((resolve, reject) => {
        setTimeout(() => resolve(`${egg} => 🍳`), 1000);
    });

<!-- getHen()
    .then(hen => getEgg(hen))
    .then(egg => cook(egg))
    .then(meal => console.log(meal));
// == -->
getHen()
    .then(getEgg)
    .then(cook)
    .catch(console.log)
    .then(console.log);
```
