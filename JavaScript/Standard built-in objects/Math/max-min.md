> Math.max() / Math.min()

- 최댓값 / 최솟값

1. Function.prototype.apply()을 사용하여 숫자 배열에서 최대 요소를 찾기

- apply() 메소드의 첫번째 파라미터로는 Math.max() 함수 내부에서 사용할 this객체를 전달해야 하는데, 여기서는 따로 this객체를 지정해 줄 필요가 없으므로 null을 전달
- apply() 메소드의 두번째 파라미터로는 Math.max() 함수로 전달할 파라미터를 배열 형태로

```
function getMaxOfArray(numArray) {
  return Math.max.apply(null, numArray);
}
```

2. spread operator

- 객체나 배열의 원소들을 하나씩 꺼내어서 펼쳐서 리턴

```
const arr = [1, 2, 3];
const max = Math.max(...arr);
```
