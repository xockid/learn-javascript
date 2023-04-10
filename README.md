# 📚 learn-javascript

> 출처: [ES2021 자바스크립트 강좌](https://www.youtube.com/playlist?list=PLcqDmjxt30RvEEN6eUCcSrrH-hKjCT4wt) 

<br>

## **목차**
  ### **1. Javascript 기초**
  + [자료형](#-자료형)  
  + [변수](#-변수)  
  + [조건문](#-조건문)  
  + [반복문](#-반복문)  
  + [객체](#-객체)  
  ### **2. Javascript 실습**
  + [DOM 객체 - 끝말잇기 게임](#-dom-객체---끝말잇기-게임)
  + [함수 - 계산기](#-함수---계산기)
  + [반복문 - 숫자야구 게임](#-반복문---숫자야구-게임)
  + [타이머 - 로또 추첨기](#-타이머---로또-추첨기)
  + [객체 - 가위바위보 게임](#-객체---가위바위보-게임)
  + [Date - 반응속도 테스트](#-date---반응속도-테스트)
  + [이차원 배열 - 틱택토 게임](#-이차원-배열---틱택토-게임)
  + [클래스 - 텍스트 RPG](#-클래스---텍스트-rpg)
  + [이벤트 루프 - 카드 짝 맞추기 게임](#-이벤트-루프---카드-짝-맞추기-게임)
  + [재귀 함수 - 지뢰찾기 게임](#-재귀-함수---지뢰찾기-게임)
  + [키보드/마우스 이벤트 - 2048 게임](#-키보드마우스-이벤트---2048-게임)
  + [마무리 - 두더지 잡기 게임](#-마무리---두더지-잡기-게임)

<br>

---

<br>

### **1. Javascript 기초**
#### 🪐 **자료형**
- **값(Value)**: 프로그램이 조작할 수 있는 데이터
- **자료형(data type)**: 값의 종류
  - **문자열(string)**: 프로그래밍에서 하나의 글자를 문자라고 하는데, 문자들이 하나 이상 나열되어 있다고 하여 문자열이라고 한다.
  - 식(또는 표현식, expression): 결괏값이 나오는 명령
  - `typeof`: 콘솔에 입력한 값의 자료형이 무엇인지 확인해주는 연산자  
  ```javascript  
  > typeof "Hello, world!";
  < "string"  

  > typeof 5;
  < "number"  

  > typeof '5';
  < "string"  
  ```
  - **비교 연산자(==)**
  ```javascript
  > '' == ' ';
  < false
  ```
  - \\(언어에 따라 백슬래시(\\)나 원화(￦) 기호로 다르게 표시): `\`를 붙이면 그다음에 나오는 문자를 기존과는 다르게 처리하라고 엔진에게 알리는 역할
  - 이스케이핑(escaping): 문자가 약속된 문법과 다르게 해석되게 하는 행위(ex. 따옴표를 이스케이핑한다.)
  - `\n`: HTML의 &lt;br&gt;태그와 같은 역할(개행)
  - 템플릿 리터럴(template literal): 백틱(``, backtick 또는 backquote)으로 감싸진 문자열  
    **백틱 문자열에서는 `\n` 문자를 사용하지 않아도 개행 가능하다.*
- **숫자**
  - 숫자(number): 소수, 음수, 지수표기법(exponential notation) 사용 가능
  - `parseInt`: 문자열을 정수로 바꿈
  - `parseFloat`: 문자열을 실수로 바꿈  
  ```javascript
  > parseInt('7');
  < 7  
  
  > typeof parseInt('7');
  < "number"  

  > parseInt('3.14');
  < 3  

  > parseFloat('3.14');
  < 3.14
  ```
  - `NaN`(Not a Number): 숫자가 아님의 약어 **하지만 typeof NaN은 "number"이다.*
  - 산술 연산자: 더하기표(+), 빼기표(-), 곱하기표(*), 나누기표(/), 나눗셈의 나머지(%), 거듭제곱(**) 등의 기호 사용
  - Infinity: 무한을 의미하는 값
  - **형 변환(type casting)**: 값의 자료형이 바뀌는 현상 또는 바꾸는 행위
  - `+ 연산자`를 사용할 때는 숫자보다 문자열 자료형이 우선시되고, `- 연산자`를 사용할 때는 다른 자료형이 먼저 숫자로 형 변환된 후 빼기를 하게 된다.
    <details>
      <summary>연산자 우선순위 표</summary>
      <div markdown="1">
        <table>
          <thead>
            <tr>
              <th>우선순위</th>
              <th>연산자(쉼표로 구분)</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>20</td>
              <td>()(그룹화)</td>
            </tr>
            <tr>
              <td>19</td>
              <td>., [], new, ()(함수 호출)</td>
            </tr>
            <tr>
              <td>18</td>
              <td>new(인수 없이)</td>
            </tr>
            <tr>
              <td>17</td>
              <td>++(후위), --(후위)</td>
            </tr>
            <tr>
              <td>16</td>
              <td>!, ~, +(단항), -(단항), ++(전위), --(전위), typeof, void, delete, await</td>
            </tr>
            <tr>
              <td>15</td>
              <td>**</td>
            </tr>
            <tr>
              <td>14</td>
              <td>*, /, %</td>
            </tr>
            <tr>
              <td>13</td>
              <td>+(다항), -(다항)</td>
            </tr>
            <tr>
              <td>12</td>
              <td><<, >>, >>></td>
            </tr>
            <tr>
              <td>11</td>
              <td><, <=, >, >=, in, instanceof</td>
            </tr>
            <tr>
              <td>10</td>
              <td>==, !=, ===, !==</td>
            </tr>
            <tr>
              <td>9</td>
              <td>&</td>
            </tr>
            <tr>
              <td>8</td>
              <td>^</td>
            </tr>
            <tr>
              <td>7</td>
              <td>|</td>
            </tr>
            <tr>
              <td>6</td>
              <td>&&</td>
            </tr>
            <tr>
              <td>5</td>
              <td>||</td>
            </tr>
            <tr>
              <td>4</td>
              <td>? :(삼항 연산자)</td>
            </tr>
            <tr>
              <td>3</td>
              <td>=, +=, -=, **=, *=, /=, %=, <<=, >>=, >>>=, &=, ^=, |=</td>
            </tr>
            <tr>
              <td>2</td>
              <td>yield, yield*</td>
            </tr>
            <tr>
              <td>1</td>
              <td>,(쉼표)</td>
            </tr>
          </tbody>
        </table>
      </div>
    </details>
  - 부동소수점 문제
    - 2진법으로 실수를 표현하면 무한 반복되는 실수가 있어 어쩔 수 없이 근삿값으로 저장되는 경우가 있다.
    - 해결법: 실수를 정수로 바꿔 계산하고 마지막에 다시 실수로 바꿈
    ```javascript
    > (0.3 * 10 - 0.1 * 10) / 10;
    < 0.2
    ```
- **불 값**
  - 불 값(boolean): `true`와 `false`를 나타내는 자료형
  - 비교 연산자: >, <, >=, <=, ==(같음), !=(같지 않음)
  - `==`과 `===`의 차이
    - ==/!= 은 값을 비교, ===/!== 은 자료형까지 비교
  - 논리 연산자
    - `&&`(AND)
    - `||`(OR)
    - `!`(true → false, false → true로 변환)
      - **!! 두 번 사용 시 값을 boolean으로 형 변환 가능**
- **빈 값 사용하기**
  - `null` (의도적으로 값을 비울 때 주로 사용)
  - `undefined` (아직 값이 설정되지 않음)  

#### 🪐 **[변수]**
- **변수(variable)**: 값을 저장하고 불러올 수 있게 하는 것  
- **선언(declaration)**: 변수를 만드는 행위  
- **초기화(initialization)**: 변수를 선언함과 동시에 값을 대입하는 행위  
- 변수를 만드는 방법은 `let`, `const`, `var` 세 가지
  - `let`, `const`는 재선언 불가, `var`은 재선언 가능  
  (크롬 개발자 도구에서는 예외적으로 let 재선언이 가능하지만 자바스트립트 표준 문법 상 let과 const 모두 재선언을 하면 에러를 내는 것이 맞다!)
  - `let`: 중복선언은 불가능하지만, 초기화 없이 재할당 가능, 블록레벨 스코프
  - `const`: 중복선언, 재할당 불가능, 블록레벨 스코프
  - `var`: 같은 이름으로 중복선언 가능, 함수레벨 스코프
```javascript
> let 변수명 = 식; //선언문
< undefined //변수 선언은 결괏값이 항상 undefined로 출력된다.  
```
```javascript
> let change = '바꿔 봐';
//let 선언'문', 문(statement)은 식과 다르게 결괏값이 없고 식의 자리에 사용할 수 없다.
< undefined;

> change = '바꿨다.'; //let이 없을 때는 코드가 식이라서 대입한 값이 결괏값으로 출력
< "바꿨다."  

//변수의 값을 비울 때
> change = null; //보통 null을 사용한다. (의도적으로 값을 지웠다는 것을 사람이 알 수 있기 때문)
< null;
```
```javascript
> let string = 'Hello, variable'; //변수를
< undefined  

> let string2 = string; //다른 변수에
< undefined  

> string2; //대입
< "Hello, variable"
```
```javascript
> let number = 7; //변수 자신을
< undefined  

> number = number + 3; //자신에 대입
< 10
//위 코드는 아래와 같이 축약 가능
> number += 3;
< 10
//같은 원리로 -=, *=, /=, %=, **= 연산자도 사용 가능
```

- `const`: 상수(constant)의 줄임말. 상수는 변하지 않는 수라는 뜻이지만, const는 엄밀히 말해 상수가 아니기 때문에 변수로 칭한다.
  - const에 객체(배열, 함수, 객체 리터럴)가 대입되면 객체 내부의 속성이나 배열의 요소는 수정할 수 있다.
  ```javascript
  const target2 = ['a', 'b', 'c', 'd', 'e'];
  target2 = ['f', 'g']; //불가능
  target2[0] = 'h'; //가능
  ```
    **코드 작성 시 변수의 값을 수정할 일이 생각보다 그리 많지 않고 실수로 값을 수정하는 일을 방지할 필요가 있을 때 상수를 사용한다.*
- `var`: 변수(variable)의 줄임말. var로 변수를 선언하면 특별히 변수문(variable statement)이라고 한다.
#### 🪐 **[조건문]**
- **조건문**: 주어진 조건에 따라 코드를 실행하거나 실행하지 않는 문.
```javascript
if (조건식) {
  실행문;
};

if (조건식) {
  실행문;
} else if (조건식) {
  실행문;
} else {
  실행문;
};
```
- 중첩 if 문
```javascript
let first = true;
let second = false;
if (first) {
  console.log('첫 번째 조건 충족!');
  if (second) {
    console.log('두 번째 조건 충족!');
  } else {
    console.log('두 번째 조건은 불충족!');
  }
} else {
  console.log('첫 번째 조건 불충족!');
}

첫 번째 조건 충족!
두 번째 조건은 불충족!
```
**중첩 if 문은 되도록 피하는 게 좋다. if - else if - else문으로 변환하여 코드 가독성을 높이자!*
- **switch 문**
```javascript
switch (조건식) {
  case 비교 조건식:
    실행문;
}
//switch 문에는 조건식 두 개 사용
//switch 옆 소괄호 조건식의 값이 case의 비교 조건식 값과 일치(===)하면 해당 실행문이 실행
//보통 조건식에 변수를 넣고, 비교 조건식에는 변수와 비교할 값을 넣는다.
```
```javascript
//if 문의 else if처럼 여러 방향으로 분기 가능
//case를 여러 번 사용하면 된다.
let value = 'F';
switch (value) {
  case 'A':
    console.log('A');
    break;
    //switch 문은 일치하는 case를 발견하면 일치 여부와 상관없이 그 아래 case들의 실행문을 모두 실행
    //원하는 결과만 얻으려면 수동으로 case에서 빠져나와야 함(break 문)
  case 'B':
    console.log('B');
    break;
  case 'C':
    console.log('C');
    break;
  default:
    //어떠한 case도 일치하지 않을 때 실행하는 case
    //case 대신 default라는 특수한 예약어를 사용
    console.log('아무것도 일치하지 않음');
}

아무것도 일치하지 않음
//default는 어디에나 위치할 수 있다! (if 문의 else와 달리 가장 처음에도 위치 가능)
```
- **조건부 연산자**
  - 조건부 연산자 또는 삼항 연산자: 분기 처리에 사용하는 또 다른 식
```javascript
조건식 ? 참일 때 실행되는 식 : 거짓일 때 실행되는 식
//조건부 연산자는 문이 아니라 식이므로 결괏값이 나온다.
```
```javascript
//조건부 연산은 조건에 따라 달라지는 값을 변수에 대입할 때 사용
> let value = 5 < 0 ? '참입니다' : '거짓입니다';
< undefined  

> value;
< "거짓입니다"
```
#### 🪐 **[반복문]**
- **while 문**
```javascript
while (조건식)
  실행문;
  //while 문은 조건식이 참인 동안 반복해서 실행문을 실행
while (조건식) {
  실행문1;
  실행문2;
  실행문3;
}  

//반복문을 멈추려면 조건식을 false로 만든다.
> let i = 0;
  while (i < 100) {
    console.log('Hello, while!');
    i++;
  }

  (100) Hello, while!
< 99
```
- **for 문**
```javascript
for (시작; 조건식; 종료식)
  실행문;
//시작(식과 변수 선언)과 조건식, 종료식
//조건식과 실행문은 while 문과 같다.  

> for (let i = 0; i < 100; i++) {
    console.log('Hello, for!');
  }

(100) Hello, for!
```
- **break 문** - 반복문 멈추기
```javascript
let i = 0;
while (true) {
  if (i === 5) break;
  i++;
}
console.log(i);

//5
```
```javascript
//무한 반복문을 표현할 때는 for 문보다 while 문을 더 많이 사용한다.
//while 문
let i = 0;
while (true) {
  console.log(i);
  i++;
}
//for 문
for (let i = 0; ; i++) {
  console.log(i);
}
```
- **continue 문** - 코드 실행 건너뛰기
```javascript
//continue 문을 넣으면 이후 코드는 건너뛴다.
let i = 0;
while (i < 10) {
  i++;
  if (i % 2 === 0) {
    continue;
  }
  console.log(i);
}

//1
//3
//5
//7
//9
```
- 중첩 반복문
```javascript
for (let i = 0; i < 10; i++) {
  for (let j = 0; j < 10; j++) {
    console.log(i, j);
  }
}

//0 0
//0 1
//0 2
//0 3
...
//9 7
//9 8
//9 9
```
```javascript
//두 번 이상 중첩되는 반복문
for (let i = 0; i < 5; i++) {
  if (i % 2 === 0) continue;
  for (let j = 0; j < 5; j++) {
    if (j % 2 === 0) continue;
    for (let k = 0; k < 5; k++) {
      if (k % 2 === 0) continue;
      console.log(i, j, k);
    }
  }
}

//1 1 1
//1 1 3
//1 3 1
//1 3 3
//3 1 1 
//3 1 3
//3 3 1
//3 3 3
```
#### 🪐 **[객체]**
- **객체(object)**: 자료형의 일종으로 다양한 값을 모아 둔 또다른 값.
- 객체의 종류는 크게 **배열(Array)**, **함수(function)**, 배열이나 함수가 아닌 객체로 나눌 수 있다.
- *배열과 함수가 객체인 이유*: 객체의 성질을 모두 다 사용할 수 있기 때문이다. 배열과 함수에도 속성들을 추가하거나 수정 및 제거할 수 있다. 객체는 함수와 배열을 포함하는 개념이라서 `{}`를 사용해 만든 객체를 **객체 리터럴**이라고 따로 부른다.
  - **배열**
  ```javascript
  //네 종류의 과일을 fruits라는 상수로 묶기
  const fruits = ['오렌지', '포도', '딸기', '복숭아'];

  //0부터 시작하는 프로그래밍 자릿수를 인덱스(index)라고 한다.
  console.log(fruits[0]);

  //오렌지  
  ```  
  - 이차원 배열: 배열 내부에 배열이 들어 있는 것
  - 배열 내부의 값은 **요소(element)** 라고 한다. 배열 이름 뒤 `.length`를 붙여 요소의 개수 구함
  ```javascript
  //배열의 마지막에 요소 추가하기
  > const target = ['가', '나', '다', '라', '바'];
    target[target.length] = '마';
    console.log(target);

    //(6) ["가", "나", "다", "라", "마", "바"]

  //혹은
  > const target = ['가', '나', '다', '라', '마'];
    target.push('바');
    console.log(target);

    //(6) ["가", "나", "다", "라", "마", "바"]

  //배열의 맨 앞에 요소 추가하기
  > const target = ['나', '다', '라', '마', '바'];
    target.unshift('가');
    console.log(target);

    //(6) ["가", "나", "다", "라", "마", "바"]

  //배열의 요소 수정하기
  > const target = ['가', '나', '다', '라', '마'];
    target[3] = '카';
    console.log(target);

    //(5) ["가", "나", "다", "카", "마"]

  //배열의 마지막 요소 제거하기
  > const target = ['가', '나', '다', '라', '마'];
    target.pop();
    console.log(target);

    //(4) ["가", "나", "다", "라"]

  //배열의 첫 번째 요소 제거하기
  > const target = ['가', '나', '다', '라', '마'];
    target.shift();
    console.log(target);

    //(4) ["나", "다", "라", "마"]

  //배열의 중간 요소 제거하기
  > const target = ['가', '나', '다', '라', '마'];
    target.splice(1, 1); //(시작 인덱스, 제거할 요소의 개수)
    console.log(target);

    //(4) ["가", "다", "라", "마"]
  //splice()에 숫자 값 하나만 넣을 시 해당 인덱스부터 끝까지 모든 요소 제거

  //배열의 요소 제거 후 자리에 다른 값 넣기
  > const target = ['가', '나', '다', '라', '마'];
    target.splice(1, 3, '타', '파');
    console.log(target);

    //(4) ["가", "타", "파", "마"]
  ```
  ```javascript
  //배열에서 요소 찾기
  > const target = ['가', '나', '다', '라', '마'];
    const result = target.includes('다');
    const result2 = target.includes('카');
    console.log(result); //includes에 주어진 값이 배열에 존재하면 true
    console.log(result2); //존재하지 않으면 false

    //true
    //false

  //배열의 요소가 몇 번째 인덱스에 위치하는지 찾기
  > const target = ['라', '나', '다', '라', '다'];
    const result = target.indexOf('다'); //indexOf는 앞에서부터 주어진 값
    const result2 = target.lastIndexOf('라'); //lastIndexOf는 뒤에서부터
    const result3 = target.indexOf('가'); //배열에 존재하지 않은 값의 인덱스는 -1
    console.log(result);
    console.log(result2);
    console.log(result3);

    //2
    //3
    //-1
  ```
  ```javascript
  //배열 반복하기
  //while 문
  > const target = ['가', '나', '다', '라', '마'];
    let i = 0;
    while (i < target.length) {
      console.log(target[i]);
      i++;
    }

    //가
    //나
    //다
    //라
    //마
    //4

  //for 문
  > const target = ['가', '나', '다', '라', '마'];
    for (let i = 0; i < target.length; i++) {
      console.log(target[i]);
    }

    //가
    //나
    //다
    //라
    //마
  ```
  - **함수**
    - 프로그래밍에서 함수(function)는 특정한 작업을 수행하는 코드를 의미
  ```javascript
  function() {} //function 예약어
  // 또는
  () => {} //화살표 함수(arrow function)

  //위는 이름이 없는 익명 함수, 아래는 일반 함수
  function a() {} //함수 선언문(function declaration statement): 함수를 상수에 대입하지 않고 function 키워드 뒤에 함수 이름을 넣음
  const b = function() {}; //함수 표현식(function expression): 상수나 변수에 대입하는 방식
  const c = () => {}; //화살표 함수

  //함수를 만드는 행위는 '선언한다'고 표현
  //만든 함수를 사용하는 행위는 '호출한다'고 표현
  ```
  ```javascript
  > function a() {}
  < undefined //함수 호출 시 항상 결괏값이 나온다. 이 값을 반환값(return value)이라고 함
  > a();
  < undefined //기본값: undefined

  //return 문을 추가하여 반환값을 직접 정할 수도 있다.
  //명시적으로 return 문을 사용하지 않을 때는 함수 실행문 끝에 return undefined가 있다고 생각
  > function a() {
      return 10;
    }
  < undefined
  > a();
  < 10

  //함수의 반환값도 '값'이다!!!
  //return 문은 함수의 실행을 중간에 멈추는 역할을 하기도 한다.
  //return 문 실행 시 그 아래 코드는 실행되지 않음.
  > function a() {
      console.log('Hello');
      return;
      console.log('Return');
    }
    a();

    Hello
  ```
  - 매개변수와 인수
  ```javascript
  > function a(parameter) { //매개변수(parameter): 함수를 선언할 때 사용한 변수
      console.log(parameter);
    }
    a('argument'); //인수(argument): 함수 호출할 때 넣은 값

    argument

  //함수는 여러 개의 매개변수와 인수를 가질 수 있고,
  //매개변수와 인수의 개수가 일치하지 않아도 된다.
  > function a(w, x, y, z) {
      console.log(w, x, y, z);
      console.log(arguments); //호출 시 넣었던 인수 목록
      //arguments 는 화살표 함수 안에서 사용 불가능. function으로 선언한 함수에서만 가능
    }
    a('Hello', 'Parameter', 'Argument');

    Hello Parameter Argument undefined
    Arguments(3) ['Hello', 'Parameter', 'Argument']

  > function a(w, x) {
      console.log(w, x);
    }
    a('Hello', 'Parameter', 'Argument');

    Hello Parameter
  ```
  ```javascript
  > function minus1(x, y) {
      const a = 100; //함수 안에서 변수나 상수 선언 가능
      return (x - y) * a;
    }
    console.log(minus1(5, 3));

    200
  //순수 함수: 자신의 매개변수나 내부 변수(또는 상수)만 사용하는 함수

  > const a = 100; //함수 바깥에 위치한 변수나 상수도 사용 가능
    function minus2(x, y) {
      return (x - y) * a;
    }
    console.log(minus2(5, 3));

    200

  /*
  함수는 자신의 매개변수나 내부에 선언한 상수나 변수가 아니더라도
  다른 상수와 변수에 접근이 가능하다.
  다만, 모든 상수나 변수에 접근할 수는 없고 스코프에 따라 접근 가능 여부가 달라짐
  */
  ```
- **객체 리터럴**
  - 객체는 여러 개의 변수를 하나의 변수로 묶을 때 사용한다.
  - 객체 리터럴: `{}`를 사용해 객체를 표현하는 것
  ```javascript
  const 객체 = {
    속성1이름: 속성1값,
    속성2이름: 속성2값,
    속성3이름: 속성3값,
  }
  ```
  ```javascript
  const lonny = {
    name: 'Frank Ocean',
    year: 1987,
    month: 10,
    date: 28,
    gender: 'M',
  };
  //속성(property): 객체 내부에 사용되는 name, year, month, date, gender 같은 정보들

  //객체의 속성 이름을 통해 속성 값에 접근
  const name = 'date';

  console.log(lonny.name); //변수.속성
  console.log(lonny ['name']); //변수[속성] *[] 내부에 문자열을 넣어야 한다!!
  console.log(lonny [name]);
  console.log(lonny.date);
  console.log(lonny ['date']);
  console.log(lonny.age); //객체 내부에 존재하지 않는 속성에 접근한다면 undefined


  Frank Ocean
  Frank Ocean
  28
  28
  28
  undefined

  //대부분은 []보다 온점을 사용해 속성에 접근
  //온점을 사용할 수 없는 경우: 대표적으로 속성 이름에 띄어쓰기나 온점이 들어 있을 때
  //이럴 때는 변수['속성 이름'] 또는 변수['속성.이름']처럼 []를 사용해서 속성에 접근

  > lonny.gender = 'None'; //변수.속성 = 값; 으로 객체 속성 수정
    console.log(lonny.gender);

    None

  > delete lonny.gender; //delete 변수.속성; 으로 객체 속성이 제거
    console.log(lonny.gender);

    undefined //제거된 속성 값은 undefined
  ```
  ```javascript
  //메서드(method): 객체의 속성 중 함수가 들어가는 속성
  const debug = {
    log: function(value) {
      console.log(value);
    },
  };
  debug.log('Hello, Method');

  //console.log 에서 log는 console 객체 안의 메서드였다!
  ```
  ```javascript
  //객체 간 비교
  > {} === {}

    false
  //객체는 모양이 같아도 생성할 때마다 새로운 객체 생성
  //따라서 같은 객체인지 비교하려면 기존 객체를 변수에 저장해 두어야 함
  > const a = {name: 'youngwon'};
    const array = [1, 2, a];
    console.log(a === array[2]);

    true
  ```
  ```javascript
  //참조(reference)
  > const a = {name: 'youngwon'};
    const b = a;
    a.name = 'kitty';
    console.log(b.name);

    kitty
  //객체를 저장한 변수를 다른 변수에 대입하면 두 변수 모두 같은 객체를 저장하는 셈!
  //위와 같은 상황일 때 변수 a와 b가 같은 객체를 참조하고 있다고 표현
  //또는 a와 b 그리고 객체 간에 참조 관계가 있다고 표현

  //다만, 객체가 아닌 값(문자열, 숫자, 불 값, null, undefined)는 다르다..
  //복사(copy): 참조가 생기지 않은 상황
  > let a = 'youngwon';
    let b = a;
    a = 'kitty';
    console.log(b);
    
    youngwon
  ```
---
> JavaScript 관련 페이지  
[모던자바스크립트 튜토리얼 (https://ko.javascript.info)](https://ko.javascript.info)  
[MDN 웹 문서 (https://developer.mozilla.org/ko/docs/Web/JavaScript)](https://developer.mozilla.org/ko/docs/Web/JavaScript)

---
### **2. Javascript 실습**
#### 🏃‍♀️ **DOM 객체 - 끝말잇기 게임**

#### 🏃‍♀️ **함수 - 계산기**
#### 🏃‍♀️ **반복문 - 숫자야구 게임**
#### 🏃‍♀️ **타이머 - 로또 추첨기**
#### 🏃‍♀️ **객체 - 가위바위보 게임**
#### 🏃‍♀️ **Date - 반응속도 테스트**
#### 🏃‍♀️ **이차원 배열 - 틱택토 게임**
#### 🏃‍♀️ **클래스 - 텍스트 RPG**
#### 🏃‍♀️ **이벤트 루프 - 카드 짝 맞추기 게임**
#### 🏃‍♀️ **재귀 함수 - 지뢰찾기 게임**
#### 🏃‍♀️ **키보드/마우스 이벤트 - 2048 게임**
#### 🏃‍♀️ **마무리 - 두더지 잡기 게임**