> async & await

- clear style of using promise
- 기존에 존재하는 promise위에 조금 더 간편한 api를 제공 (syntactic sugar)

1. async

- 함수 앞에 async 키워드를 쓰면 코드블록이 promise로 자동으로 바뀌게 됨.

```
async function fetchUser(){
    // do network request in 10 secs...
    return 'ellie';
}

const user = fetchUser();
user.then(console.log);
console.log(user);
```

2. await

-

```
function delay(ms){
    return new Promise(resolve => setTimeout(resolve, ms));
}
async function getApple(){
    await delay(3000);
    return '🍎';
}
async function getBanana(){
    await delay(1000);
    return '🍌';
}
<!-- function getBanana(){
    return delay(1000)
    .then(()=>'🍌');
} -->


// 콜백지옥
<!-- function pickFruits(){
    return getApple().then(apple => {
        return getBanana().then(banana => `${apple} + ${banana}`);
    });
} -->

async function pickFruits(){
    // 병렬적으로, 동시에 실행하게 하기 위해 promise를 만들어준 후, 동기화 => 그러나 이렇게 안씀
    const applePromise = getApple();
    const bananaPromise = getBanana();
    const apple = await applePromise;
    const banana = await bananaPromise;
    return `${apple} + ${banana}`;
}
pickFruits().then(console.log);
```

3. useful Promise APIs

- 위 코드를 간단하게 만들 수 있음
- Promise.all([]) 프로미스 배열을 전달해 모든 프로미스들이 병렬적으로 다 받을 때까지 모아주는 API.

```
function pickAllFruits(){
    return Promise.all([getApple(), getBanana()])
    .then(fruits => fruits.join(' + '));
}
pickAllFruits().then(console.log);

```

- Promise.race() 가장 먼저 값을 리턴하는 아이만 전달되어짐(setTimeout 시간이 다를때)

```
function pickOnlyOne(){
    return Promise.race([getApple(), getBanana()]);
}
pickOnlyOne().then(console.log);
```
