# Day 1
- JS 입문
  - 크롬 > `F12` > `Console`에서 인터프리터 방식으로 실행 가능
  - `console.log()`
  
    ```
    > console.log("Hello world");
    Hello world
    ```

    ![codeset snapshot](img/day01/day01-01.png)

- 코드 작성 규칙
  - 주석은 `//` 나 `/* ... */`로 처리
  - 들여쓰기는 C언어처럼. 편의를 위해서 들여쓰기.

- 자료형 - 문자열
  - `typeof` 연산자(operator)

    ```
    > typeof 'Hello, world'
    < 'string'
    ```

    ![codeset snapshot](img/day01/day01-02.png)

  - 비교 연산자 `==`

    ```
    > '' == ''
    < true
    > '' == ' '
    < false
    ```

  - 문자열 안에 따옴표 사용하기

    ```
    > 'backslash(\) in string'
    < 'backslash() in string'
    ```

    ![codeset snapshot](img/day01/day01-03.png)

  - 한 문자열을 여러 줄로 표시하기 : `\n`을 사용하고, `alert()`도 사용해보기

    ![codeset snapshot](img/day01/day01-04.png)
    ![codeset snapshot](img/day01/day01-05.png)

  - 템플릿 리터럴 사용하기 : backquote 사이의 문자열 \`...\` 을 사용하면 행갈이가 편하다.

    ![codeset snapshot](img/day01/day01-06.png)

# Day 2

- 자료형 - 숫자
  
  - 웹사이트 DevTools에서 이진수, 16진수 등을 바로 확인할 수 있다니! 매우 유용할듯!
    ```
    > 0b11
    < 3
    > 0xabab
    < 43947
    ```
  
  - string to int : `parseInt()`, `parseFloat()`, `Number()`
  
    ![codeset snapshot](img/day02/day02-01.png)
  
    `parseInt()` can be used to invert base of the numbers. [ 2진수 111 == 10진수 7 ] 이고, [ 7진수 111 == 10진수 57 ] 임을 생각해보면

    ![codeset snapshot](img/day02/day02-02.png)

  - NaN
    
    `typeof NaN` ==> `'number'` ..?? OMG..
  
  - 무한값 `Infinity`

    ![codeset snapshot](img/day02/day02-03.png)

    이게뭐람

  - 문자와 숫자 더하기 : Type casting. 

    ![codeset snapshot](img/day02/day02-04.png)

    \+는 append 느낌, \-는 진짜 빼기. JS는 엄청나군.

  - 연산자 우선순위
    
    ![contents of a book](img/day02/day02-05.jpg)

  - 실수 연산

    ![codeset snapshot](img/day02/day02-06.png)

    (당연함)

- 자료형 - `Boolean`

  - `NaN`이 포함된 비교는 `!=`이 아니면 무조건 `false`다.

    ![codeset snapshot](img/day02/day02-07.png)

  - 자동 type casting

    ![codeset snapshot](img/day02/day02-08.png)

  - `.charCodeAt()` : char to ascii code

    ```
    > 'a'.charCodeAt();
    < 97
    ```
  
  - `==` 와 `===`

    자동 type casting 없이 비교하려면 `===`와 `!==`를 사용하면 된다.

  - falsy value : 형 변환 후 `false`가 되는 값. ex) `false`, `''`, `0`, `NaN`, `undefined`, `null` (<-> truthy value)
  
    ![codeset snapshot](img/day02/day02-09.png)

  - and operator `&&`, or operator `||`, nullish coalescing operator `??`
  
    - `x && y` : `y` if `x` is true, else `x`
    - `x || y` : `x` if `x` is true, else `y`
    - `x ?? y` : `y` if `x` is (null or undefined), else `x`

    ![codeset snapshot](img/day02/day02-10.png)
  
- 자료형 - 빈 값 사용하기

  - `undefined` : 값이자 자료형임 (`undefined`라는 type을 가진 값은 `undefined` 밖에 없음). 반환할 결과 값이 없을 때 `undefined`가 반환됨.
    
    ![codeset snapshot](img/day02/day02-11.png)

  - `null` : 값이자 자료형임 (`null`라는 type을 가진 값은 `null` 밖에 없음. 아래 codeset의 `typeof`의 결과는 JS의 고질적인 버그(??!!))

    ![codeset snapshot](img/day02/day02-12.png)

# Day 3

- 변수 선언 

  - `let`

    ```
    > let total = 5 + 8;
    < undefined
    > total;
    < 13

    > let empty;
    < undefined
    > empty;
    < undefined
    ```

  - `const` : 상수를 선언할 때 사용. 초기화하지 않으면 에러가 남.

  - `var` : 옛날에 많이 사용했었음.

- 조건문

  - ![codeset snapshot](img/day03/day03-01.png)
  - ![codeset snapshot](img/day03/day03-02.png)
  - ![codeset snapshot](img/day03/day03-03.png)
  - `if` - `else if` - `else` 존재.
  - `switch` - `case` 존재.
  - 삼항 연산자 `(condition) ? (when true) : (when false)` 존재.
  
# Day 4

- 반복문
  - `while`, `for(시작; 조건식; 종료식)`, `break`, `continue`
  
- 객체 - 배열
  
  - array 생성하기
  
    ![codeset snapshot](img/day04/day04-01.png)
  
  - element 개수 구하기 : `.length`  +) `.at()`
  
    ![codeset snapshot](img/day04/day04-02.png)
  
  - element 추가하기 : `.unshift()`, `.push()`
  
    ![codeset snapshot](img/day04/day04-03.png)
  
  - element 삭제하기 : `.pop()`, `.shift()`, `.splice()`
  
    ![codeset snapshot](img/day04/day04-04.png)
    ![codeset snapshot](img/day04/day04-05.png)

  - element 찾기 : `.includes()`, `.indexOf()`, `.lastIndexOf()`... naming convention이 어우....

    ![codeset snapshot](img/day04/day04-06.png)
    ![codeset snapshot](img/day04/day04-07.png)

  - array 자르고 합치기 : `<array>.slice(<start>, <end>)`, `<array>.concat(...)`

    ![codeset snapshot](img/day04/day04-08.png)

    흠.. 전체적으로 얼렁뚱땅 진행되는 언어인가.. 에러도 안 나고..

  - array와 string 간의 변환 : `.join()`, `.split()`

    ![codeset snapshot](img/day04/day04-09.png)
