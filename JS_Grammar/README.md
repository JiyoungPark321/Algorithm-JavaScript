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

#### 2) Number.MIN_SAFE_INTEGER

- JS 에서 안전한 최소 정수값을 나타낸다. (-(2^53 - 1))



##### - array method

### 4. array - push(), pop(), sort(), splice()

- 배열 : 값을 순차적으로 저장하는 용도로 사용

- `[ ] (대괄호)` 를 사용해 표기하며 데이터 타입 제약없이 내부 값으로 사용 가능

- ```javascript
  let array = [1, 2, 3];
  
  // 배열 요소에 접근하기
  console.log(array[0]);   // 1
  console.log(array[2]);   // 3
  
  // 배열 요소의 개수 확인하기
  console.log(array.length);   // 3
  
  // 마지막 요소에 접근하기
  console.log(array[array.length -1]);   // 3
  ```



### 4-1. array.push()

- 배열의 마지막에 새로운 요소를 추가한 후, 변경된 배열의 길이를 반환

- ```javascript
  let arr = [1, 2, 3];
  
  arr.push("new");    // 3
  
  console.log(arr);   // [1, 2, 3, 'new'];
  ```

- 



### 4-4. array.splice()

- 배열에 추가/제가/교체/추출 가능

  ```javascript
  arr.splice(start, count, [value1], [value2],...)
  ```

  

#### 1. 배열에 요소 추가하기

```javascript
let arr = [0, 1, 2, 3];

// 배열 2번째 위치한 곳에 숫자 5를 추가
arr.splice(2, 0, 5);
// [0, 1, 5, 2, 3]

// 배열 2번째 위치한 곳에 숫자 5, 7 을 추가
arr.splice(2, 0, 5, 7);
```



#### 2. 배열 요소 제거하기

```javascript
let arr = [0, 1, 2, 3];

// 배열 1번째부터 1개 제거
arr.splice(1, 1);
// [0, 2, 3]

// 배열 1번째부터 2개 제거
arr.splice(0, 3);
```



#### 3. 배열 요소 교체하기

```javascript
let arr = [0, 1, 2, 3];

// 배열 1번째부터 1개를 제거하고 숫자 5 추가
arr.splice(1, 1, 5);
// [0, 5, 2, 3]

// 배열 1번째부터 2개 제거하고 숫자 10, 11 추가
arr.splice(0, 10, 11, 3);
```



#### 4. 배열 요소 추출하기 (제거한걸 변수에 담아주면 됨)

```javascript
let arr = [0, 1, 2, 3];

// 배열 1번째부터 1개를 제거 후 새로운 변수 newArr에 담아주기
let newArr = arr.splice(1, 1);
// [1]

// 배열 1번째부터 2개 제거 후 새로운 변수 newArr에 담아주기
let newArr = arr.splice(1, 2);
// [1, 2]
```

​      

##### - array 함수 3대장 : map, filter, reduce

### 5. reduce, reduceRight

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





### 6. filter()

- 참고문서 : https://7942yongdae.tistory.com/49

- 배열을 순회하며 요소마다 조건 확인 후 조건을 만족하는 원소들로 구성된 새로운 배열을 리턴한다.

```javascript
Array.prototype.filter(callback[, thisArg])
```

- 주어진 배열의 값들을 오름차순으로 접근해 callbackfn을 통해 true를 반환하는 요소를 기준으로 신규 배열을 만들어 반환한다.

```javascript
const numbers = [1];

numbers.filter((number, index, source) => {
    // number : 요소값
    // index : source에서 요소의 index
    // source: 순회하는 대상
    
    console.log(number);
    // 1
    
    console.log(index);
    // 0
    
    console.log(source);
    // [1]
    
    return number > 3;
});

```



- 예제1 :  3보다 큰 수 거르기

  ```javascript
  const numbers = [1, 2, 3, 4, 5];
  const result = numbers.filter(number => number > 3);
  
  console.log(numbers);
  // [1, 2, 3, 4, 5]
  
  
  console.log(result);
  // [4, 5]
  ```

  - for문을 사용할 수 있지만 권장하지 않는다.

  

- 예제2 : JSON 배열 사용법

  ```javascript
  const guys = [
      {name: 'TOM', money: 500 },
      {name: 'JHONE', money: 400 },
      {name: 'JAMES', money: 300 },
      {name: 'KIM', money: 20 }
  ];
  
  const rich = guys.filter(man => man.money > 300);
  
  console.log(rich);
  // [
  //	{name: 'TOM', money: 500 },
  //	{name: 'JHONE', money: 400 }
  // ]
  ```



- 예제3 : 다중 조건 사용하기

  ```javascript
  const numbers = [1, 2, 3, 4, 5];
  
  const result = numbers.filter(number => {
      if (number) > 1 && number < 5 {
      	return true;   
      }
      return false;
  })
  
  console.log(result);
  // [2, 3, 4]
  ```




- 예제 4 : 고차 함수

- 배열 객체 메서드 중에 map, filter, reduce, forEach 등은 고차함수 이다.

- 고차함수란?  

  - 함수의 인수로 함수를 전달 받을 수 있는 함수를 고차함수라고 한다.
  - 인자로 전달되는 함수를 콜백함수라고 한다.

  ```javascript
  const numbers = [1, 2, 3, 4, 5];
  
  const greaterThanThree = value => value > 3;
  
  const newNumbers = numbers.filter(greaterThanThree);
  // or
  // const newNumbers = numbers.filter(function(v, i){
  //     return v > 3;
  // })
  
  console.log(newNumbers);
  // [4, 5]
  ```

  





### 7. map()





### 8. replace()

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

- `/` 뒤에는 `g` 라는 modifier 를 붙인다. 여기서 `g` 는 global match 라는 의미

  ```javascript
  let fruits = 'apple, banana, orange, strawberry, Banana';
  let replaced_fruits = fruits.replace(/banana/g, 'tomato');
  
  console.log(replaced_fruits)
  // apple, tomato, orange, strawberry, Banana
  ```

  

- 대소문자 구분없이 모든 문자열을 치환하고 싶을 때는 `i` 라는  modifier 를 사용하면 되므로 `i`와 `g`를 함께 적어주면 된다.

  ```javascript
  let fruits = 'apple, banana, orange, strawberry, Banana';
  let replaced_fruits = fruits.replace(/banana/gi, 'tomato');
  
  console.log(replaced_fruits)
  // apple, tomato, orange, strawberry, tomato
  ```

  

### 9. split(), substr(), substring()

#### 1. split()

- 문자열을 분할하는 메서드

- string.split(separator, limit)   :  문자열을 separator로 잘라서 limit 크기 이하의 배열에 잘라진 문자열을 저장해 리턴.

- separator

  - 필수 x
  - 문자열을 잘라주는 구분자
  - 값이 입력되지 않으면 문자열 전체를 배열에 담아서 리턴

  ```javascript
  let string1 = 'apple,banana,orange';
  string1.split(',');
  // ["apple", "banana", "grape"]
  ```

- limit

  - 필수 x
  - 최대 분할 개수

  ```javascript
  let string2 = 'water,coke,juice';
  string2.split(',', 2);
  //["water", "coke"]
  ```

- ex

  - Separator가 맨 앞 or 맨 뒤에 있을 경우 빈 문자열로 반환됨.

  ```javascript
  let str='COMPUTERPROGRAMMINGR';
  let newStr = str.split('R');
  console.log(newStr);
  // ["COMPUTE", "P", "OG", "AMMING", ""]
  
  let str1='RRCOMPUTERPROGRAMMINGRRR';
  let newStr1 = str.split('R');
  console.log(newStr);
  // ["", "", COMPUTE", "P", "OG", "AMMING", "", "", ""]
  ```




#### 2. substr()

- substr(시작인덱스, 길이)

```javascript
let letter = '12348439';
let newLetter = a.substr(2,5);

console.log(newLetter);
//34843
```



#### 3. substring()

- substring(시작인덱스, 종료인덱스-1)

```javascript
let letter = '12348439';
let newLetter2 = a.substr(2,5);

console.log(newLetter2);
// 348
```





### 10. ASCII (American Standard Code for Information Interchange, 아스키)

- A ~ Z  : 65 ~ 90
- a ~ z   :   97 ~ 122



#### 1. charAt()

```javascript
let letter = 'coding';
console.log(letter.charAt(0));
// c

console.log(letter.charAt(length -1));
// g

console.log(letter.charAt(1000) == '');
// true
```



#### 2. charCodeAt()

- 문자열중 하나를 선택해 아스키코드 번호로 변환해주는 함수

```javascript
let letter = 'a'
let num = letter.charCodeAt();

console.log(num);
// 97
```



#### 3. String.fromCharCode()

- 아스키코드번호를 받아 문자열을 반환해주는 함수

```javascript
let answer = "";
answer += String.fromCharCode(97);
console.log(answer);
// a

answer += String.fromCharCode(100, 101, 103);
console.log(answer);
// adeg
```





### 9. toUpperCase(), toLowerCase()

#### 1. toUpperCase()

- string.toUpperCase()

- 이 메서드는 문자열을 대문자로 변환해 반환. (문자 자체를 바꾸진 않음)

  ```javascript
  console.log('alphabet'.toUpperCase());
  // 'ALPHABET'
  ```



#### 2. toLowerCase()

- string.toLowerCase()

- 이 메서드는 문자열을 소문자로 변환해 반환. (문자 자체를 바꾸진 않음)

  ```javascript
  console.log('ALPHABET'.toUpperCase());
  // 'alphabet'
  ```

  





### 11. 논리 연산자 (AND, OR, NOT)

#### 1. `&&` (AND)

#### 2. `||` (OR)

#### 3. `!` (NOT)





### 12. 사칙연산자

#### 1. 나눗셈

##### 1-1. 몫 ,  parseInt(string, n)

```javascript
let result = parseInt(13 / 5)

console.log(result);
// 2
```

##### - parseInt 란?

- string 을 n 진법일 때의 값으로 바꾼다. 

- n은 옵션으로 2부터 36까지 입력 가능하다.

- 입력하지 않으면 10으로 처리한다.

- ```javascript
  parseInt('100', 2)
  // 4
  parseInt('12.6738')
  // 12
  ```

- 

##### 1-2 나머지, %





### 13. indexOf

- 문자열에서 특정 문자열의 위치를 찾고 검색된 문자열이 <b>첫번째</b>로 나타나는 위치 index를 리턴한다.

- ```javas
  string.indexOf(찾을 문자열, 찾기 시작할 위치)
  ```

  - 찾기 시작할 위치는 option

- 찾는 문자열이 없으면 -1을 리턴한다.

- 문자열을 찾을 때 대소문자를 구분한다.

```javascript
let string = 'applebanana';

console.log(string.indexOf("p"));
// 1

console.log(string.indexOf("an"));
// 6
```

- 리스트인 경우

```javascript
let newList = ["포도", "딸기", "수박", "참외", "자두"];

console.log(newList.indexOf("딸기"));
// 1

console.log(newList.indexOf("딸"));
// -1
```





- 











