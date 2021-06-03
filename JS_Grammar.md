# JavaScript - 문법 정리



[toc]





### 1. Math 

- https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Math

#### 1) Math.ceil (올림)

- 소수값이 존재할 때 값을 올리는 역할을 하는 함수

  ```javascript
  let num = 3.5;
  console.log(Math.ceil(num));
  // 4
  ```

  

#### 2) Math.floor (내림)

- 소수값이 존재할 떄 소수값을 버리는 역할을 하는 함수

  ```javascript
  let num = 3.5;
  console.log(Math.floor(num));
  // 3
  ```

  

#### 3) Math.round (반올림)

- 소수값에 따라 올리거나 버리는 역할

  ```javascript
  let num = 3.5;
  console.log(Math.round(num));
  // 4
  ```



#### 4) Math.max()

- 입력값으로 받은 0개 이상의 숫자 중 가장 큰 숫자를 반환

  ```javascript
  Math.max(10, 20);
  // 20
  
  let arr = [1, 2, 3];
  let result = Math.max(...arr);
  // 3
  ```

- 아무 요소도 넣지 않는다면 `Math.max()  ` `-Infinity` 로 반환한다.

- 한 개 이상의 요소가 숫자로 변환되지 않는다면 `NaN` 로 반환된다.

- spread operator 를 사용하지 않고 `arr (배열)` 을 넣으면 `NaN` 가 뜬다. → 인자를 넣어줘야 한다.  

  

#### 5) Math.min()

- 주어진 숫자들 중 가장 작은 값을 반환

  ```javascript
  Math.min(10, 20, 30);
  // 10
  
  let arr = [1, 2, 3];
  let result = Math.max(...arr);
  // 1
  ```

- 아무 요소도 넣지 않는다면 `Math.max()` `Infinity` 로 반환한다.

- 한 개 이상의 요소가 숫자로 변환되지 않는다면 `NaN` 로 반환된다.

- spread operator 를 사용하지 않고 `arr (배열)` 을 넣으면 `NaN` 가 뜬다. → 인자를 넣어줘야 한다. 



### 2. 반복문

#### 1) for 문

```javascript
let result = 0;
for (let i = 0; i < 10; i++) {
    result += i;
}
return result;
```

- for (시작; 조건; 끝) { 내용 }



#### 2) for / of 문

- 반복할 수 있는 객체(iterable objects) 를 순회할 수 있도록 해주는 반복문

- 자바스크립트에서 반복할 수 있는 객체에는 Array, Map, Set, arguments 객체 등이 있다.

- 이 반복문은 루프마다 객체의 열거할 수 있는 속성 값을 지정된 변수에 대입 한다.

  ```javascript
  for (변수 of 객체) {
  	반복적으로 실행하고자 하는 실행문;
  }
  ```

  ```javascript
  let arr = [1, 3, 25, 32, 463]
  let answer = 0
  for (let x of arr) {
      answer += x;
  }
  console.log(answer);
  ```

  

#### 3) While 문

```javascript
let result = 0;
let i = 0;
while (i < 10) {
    result += i;
    i++;
}
return result;
```



#### +) break, continue

- break 는 반복문 안에 넣으면 반복문을 중단 할 수 있다.
- continue 는 반복문을 끝까지 돌긴 하지만 continue가 있는 아랫부분은 실행하지 않고 다음 반복문으로 넘어간다.



### 3. Number

- https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Number

#### 1) Number.MAX_SAFE_INTEGER

- JS 에서 안전한 최대 정수값을 나타낸다. (2^53 - 1)





### 4. reduce, reduceRight

#### 1. reduce

- `배열.reduce((누적값, 현재값, 인덱스, 요소) => { return 결과}, 초기값);`

  ```javascript
  const arr = [1, 2, 3];
  
  result = arr.reduce((acc, cur, i) => {
      console.log(acc, cur, i);
      return acc + cur;
  }, 0);
  // 0 1 0
  // 1 2 1
  // 3 3 2
  result;
  // 6
  ```

- 초기 값을 적지 않으면 0번째 인덱스가 초기값이 된다.

  ```javascript
  const arr = [1, 2, 3];
  
  result = arr.reduce((acc, cur, i) => {
      console.log(acc, cur, i);
      return acc + cur;
  });
  // 초기값 = 1
  // 1 2 1
  // 3 3 2
  result; 
  // 6
  ```

- 요소란?

  ```javascript
  const arr = [1, 2, 3, 4, 5];
  
  result = arr.reduce((acc, cur, i, e) => {
      console.log(acc, cur, i, e);
      return acc + cur;
  }, 0;
  
  result; 
  // 0 1 0 [1, 2, 3, 4, 5]
  // 1 2 1 [1, 2, 3, 4, 5]
  // 3 3 2 [1, 2, 3, 4, 5]
  // 6 4 3 [1, 2, 3, 4, 5]
  // 10 5 4 [1, 2, 3, 4, 5]
  // 15
  ```

  

#### 2. reduceRight

- reduce 와 동작은 같지만 요소 순회를 오른쪽에서부터 왼쪽으로 한다.

  ```javascript
  const arr = [1, 2, 3];
  
  result = arr.reduce((acc, cur, i) => {
      console.log(acc, cur, i);
      return acc + cur;
  }, 0);
  // 0 3 2
  // 3 2 1
  // 5 1 0
  result; 
  // 6
  ```

  

#### 5. array.splice()

- 배열에 추가/제가/교체/추출 가능

  ```javascript
  arr.splice(start, count, [value1], [value2],...)
  ```

  

##### 1. 배열에 요소 추가하기

```javascript
let arr = [0, 1, 2, 3];

// 배열 2번째 위치한 곳에 숫자 5를 추가
arr.splice(2, 0, 5);
// [0, 1, 5, 2, 3]

// 배열 2번째 위치한 곳에 숫자 5, 7 을 추가
arr.splice(2, 0, 5, 7);
```



##### 2. 배열 요소 제거하기

```javascript
let arr = [0, 1, 2, 3];

// 배열 1번째부터 1개 제거
arr.splice(1, 1);
// [0, 2, 3]

// 배열 1번째부터 2개 제거
arr.splice(0, 3);
```



##### 3. 배열 요소 교체하기

```javascript
let arr = [0, 1, 2, 3];

// 배열 1번째부터 1개를 제거하고 숫자 5 추가
arr.splice(1, 1, 5);
// [0, 5, 2, 3]

// 배열 1번째부터 2개 제거하고 숫자 10, 11 추가
arr.splice(0, 10, 11, 3);
```



##### 4. 배열 요소 추출하기 (제거한걸 변수에 담아주면 됨)

```javascript
let arr = [0, 1, 2, 3];

// 배열 1번째부터 1개를 제거 후 새로운 변수 newArr에 담아주기
let newArr = arr.splice(1, 1);
// [1]

// 배열 1번째부터 2개 제거 후 새로운 변수 newArr에 담아주기
let newArr = arr.splice(1, 2);
// [1, 2]
```



#### 5. replace()

- 문자열에서 변경하려는 문자열이 여러번 반복될 경우, 첫번째로 발견한 문자열만 치환한다.

  ```javascript
  let test = 'BANANA';
  let result = test.replace('A', '@');
  
  console.log(result);
  // B@NANA
  ```

- 아쉽게도 replaceAll() 이라는 함수는 없음

- 모두 바꾸려면 정규 표현식(regular expression) 을 사용해야 한다.

- 정규식으로 찾으려는 문자열은 `/` 로 감싸서, 파라미터로 들어가는 값이 정규식임을 알려준다.

- `/` 뒤에는 `g` 라는 modifier 를 부