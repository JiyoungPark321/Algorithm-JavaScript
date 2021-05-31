# JavaScript - 문법 정리



### 목차

[1. Math](#1.-math)

[2. 반복문](#2.-반복문)







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













