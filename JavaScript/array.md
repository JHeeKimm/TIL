> Array

- 자료구조 : 비슷한 종류의 데이터들을 묶어서 한데다 보관하는 것.
- object는 프로퍼티와 메소드로, 서로 연관된 특징과 또는 행동들을 묶어 놓는 것.
- 비슷한 타입의 object들을 묶어 놓는 것이 자료구조.
- 검색, 삽입, 삭제, 정렬

- Array
  - 칸칸이 촘촘히 모여있는 자료구조.
  - 인덱스 번호가 매겨져 있음.
  - 한 배열 안에는 동일한 타입을 담는게 좋음(js에서는 다른 타입도 가능해서..)

1. Declaration

```
const arr1 = new Array();
const arr2 = [1, 2];
```

2. Index position

```
const fruits = ['🍎', '🍌'];
console.log(fruits);
console.log(fruits.length); // 2
console.log(fruits[0]); // 🍎
console.log(fruits[1]); // 🍌
console.log(fruits[2]); //undefined
console.log(fruits[fruits.length - 1]); // 🍌
```

3. Looping over an array

- print all fruits

```
// a. for
for(let i = 0; i < fruits.length; i++){
    console.log(fruits[i]);
}

// b. for of
for(let fruit of fruits){
    console.log(fruit);
}

// c. forEach //콜백함수를 받아옴, 배열안에 들어있는 value들 마다 내가 전달한 함수를 출력해냄
fruits.forEach((fruit) => console.log(fruit));
```

4. Addtion, deletion, copy

- push : add an item to the end

```
fruits.push('🍇', '🍋');
console.log(fruits);
```

- pop : remove an item from the end

```
fruits.pop(); // 뒤에부터 하나씩 없어짐
console.log(fruits);
```

- unshift : add an item to the beginning

```
fruits.unshift('🍓', '🍑');
console.log(fruits);
```

- shift : remove and item from the beginning

```
fruits.shift();
console.log(fruits);
```

=> shift, unshift are slower than pop, push.

- splice : remove an item by index position

```
fruits.splice(1); // 인덱스 1부터 모든 데이터 지움
fruits.splice(1, 1); // 인덱스 1부터 1개만 지움
fruits.splice(1, 1, '🍒', '🍉'); // 지워진 자리에 '🍒', '🍉' 추가됨
fruits.splice(1, 0, '🍒', '🍉'); // 지우지 않고 '🍒', '🍉' 추가됨
```

- combine tow arrays

```
const fruits2 = ['🍐', '🍍'];
const newFruits = fruits.concat(fruits2);
console.log(newFruits); // fruits뒤에 fruits2 배열이 합쳐서 새로운 배열을 리턴함
```

5. Searching

```
// indexOf : find the index
console.clear();
console.log(fruits);
console.log(fruits.indexOf('🍎')); // 0 제일 첫번째로 들어있는 값의 인덱스

// includes
console.log(fruits.includes('🍎')); // true

// lastIndexOf
console.log(fruits.lastIndexOf('🍎')) // 제일 마지막으로 들어있는 값의 인덱스

```

> Quiz ( Array APIs )

```

// Q1. make a string out of an array
{
  const fruits = ['apple', 'banana', 'orange'];
  const result = fruits.join(','); // 'apple,banana,orange'
  console.log(result);

  // join은 구분자를 자유롭게 넣을 수 있다는 것이 toString과의 차이이다.
}

// Q2. make an array out of a string
{
  const fruits = '🍎, 🥝, 🍌, 🍒';
  const result = fruits.split(',', 2); // 첫번째, 두번째까지의 것만 받아와서 배열로 만듦
  console.log(result);
}

// Q3. make this array look like this: [5, 4, 3, 2, 1]
{
  const array = [1, 2, 3, 4, 5];
  const result = array.reverse(); // 배열 자체를 변환하고, 변환한 리턴값 배열을 반환함
  console.log(result);
  console.log(array);

  // array.sort((a, b) => b - a);
}

// Q4. make new array without the first two elements
{
  const array = [1, 2, 3, 4, 5];
  // consnt result = array.splice(0, 2); // 배열 자체에서 0번부터 2개를 삭제해버림
  consnt result = array.slice(2, 5); // 원래 배열은 바뀌지 않고, 2번부터 5번전까지 새배열로 받아옴
  console.log(result); // [3, 4, 5]
  console.log(array); // [1, 2, 3, 4, 5]

  // splice : 배열 자체 수정
  // slice : 배열에서 원하는 부분만 리턴해서 받아오고 싶을 때 사용
}

class Student {
  constructor(name, age, enrolled, score) {
    this.name = name;
    this.age = age;
    this.enrolled = enrolled;
    this.score = score;
  }
}
const students = [
  new Student('A', 29, true, 45),
  new Student('B', 28, false, 80),
  new Student('C', 30, true, 90),
  new Student('D', 40, false, 66),
  new Student('E', 18, true, 88),
];

// Q5. find a student with the score 90
{
    const result = students.find((student) => student.score === 90);
    console.log(result);
    // find: 콜백함수가 true/false 값을 반환하면 find함수는 true인 배열의 요소를 찾아준다.
}

// Q6. make an array of enrolled students
{
    const result = students.filter((student) => student.enrolled);
    console.log(result);
}

// Q7. make an array containing only the students' scores
// result should be: [45, 80, 90, 66, 88]
{
    const result = students.map((student) => student.score);
    console.log(result);
    // map: 배열안에 들어있는 요소 한가지 한가지를 다른 것으로 변환해주는 것.
}

// Q8. check if there is a student with the score lower than 50
{
    const result = students.some((student) => student.score < 50);
    console.log(result);
    // some: 배열의 요소 중에서 콜백함수가 리턴이 true가 되는 애가 있는지 없는지 확인해주는 것. 배열 중에 어떤 것이라도 만족되는 것이 있는지 확인할 때 사용.

    const result2 = !students.every((student) => student.score >= 50);
    console.log(result2);
    // every: 모든 배열의 조건이 만족되어야 할 때 사용.
}

// Q9. compute students' average score
{
    const result = students.reduce((prev, curr) => prev + curr.score, 0);
    console.log(result / students.length);

    // initialValue 0부터 시작하게 설정
    // reduce: 원하는 시작점부터 배열에 있는 모든 요소들의 값을 누적하는, 함께 모아놓을 때 사용.
    // reduceRight: 배열의 뒤에서부터 시작
    // prev: 이전에 콜백함수에서 리턴된 값이 전달되어져 옴
    // curr: 배열의 아이템을 순차적으로 전달 받음
}

// Q10. make a string containing all the scores
// result should be: '45, 80, 90, 66, 88'
{
    const result = students.map((student) => student.score).join();
    console.log(result);
}

// Bonus! do Q10 sorted in ascending order
// result should be: '45, 66, 80, 88, 90'
{
    const result = students.map((student) => student.score).sort((a, b) => a - b).join();
    console.log(result);
}
```
