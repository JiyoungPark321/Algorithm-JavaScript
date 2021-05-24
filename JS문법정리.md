# JavaScript - 문법 정리



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



#### 2) While 문

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

















