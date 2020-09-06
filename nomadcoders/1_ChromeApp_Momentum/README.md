# Chrome App - Momentum

Momentum on Vanilla JS

From https://nomadcoders.co/javascript-for-beginners/lobby

<br>

## :star2: ​Features

- Clock
- To Do List
- Weather
- Daily Quote
- Daily Photo
- Offline Support

<br>

## :memo: ​MEMO

- Vanilla JS: JavaScript의 한 종류로, 라이브러리가 없는 JavaScript를 의미

- JavaScript: ECMAScript 사양을 준수하는 범용 스크립팅 언어
- ECMAScript: ECMAScript specification. 스크립트언어가 준수해야 하는 규칙이나 지침을 제공(ES5, ES6 ...)

<br>

- JS 파일은 항상 body 제일 마지막에 추가
- `<script ... />`가 아니라 `<script ...></script>`로 닫아줘야 함

<br>

- `var`: ES6 이후에 `var`가 가진 문제점들을 해결하기 위해 `let`, `const`가 등장
  - 같은 변수명을 여러 번 선언(재선언)해도 에러 X
  - 변수가 선언되지 않았는데도 참조 가능(undifined)
- `const`: 선언 및 초기화 이후에 값 변경 X
- `let`: 선언 및 초기화 이후에 변경 O

- [호이스팅(Hoisting)이란?](https://gmlwjd9405.github.io/2019/04/22/javascript-hoisting.html)

  - 함수 내부에 선언들을 유효범위 최상단으로 끌어올리는(Hoisting) 것

  - 자바스크립트 Parser가 함수 실행 전 함수 내부를 한 번 훑으면서, 함수 내부의 **변수/함수 선언(할당 X)** 을 내부적으로 맨 위로 끌어올림

  - 끌어올려진 변수/함수 선언의 유효범위는 `{}` 내부

  - `var` 변수/함수에서만 호이스팅이 일어남(`let, const` 변수 선언과 함수 표현식은 호이스팅 X)

    ```javascript
    // code
    console.log(a);   // undefined
    var a = "aaa";
    let b = "bbb";
    ```

    ```javascript
    // hoisting
    var a;
    console.log(a);
    a = "aaa";
    let b = "bbb";
    ```

    - 위의 code는 내부적으로 아래와 같이 작동함. 따라서 `var a = "aaa";` 코드 중 `var a` 의 선언부만(할당부 X) 맨 위로 끌러올려져서 `console.log(a);` 라인이 문제 없이 작동함(`undefined` 출력)
    - `let b = "bbb";` 는 `let` 변수이기 때문에 호이스팅이 일어나지 않음

    <br>

    ```javascript
    // code
    foo();
    foo2();   // error
    
    function foo() { ... } // 함수 선언문
    var foo2 = function() { ... } // 함수 표현식
    ```

    ```javascript
    // hoisting
    var foo2;
    function foo() { ... }
    
    foo();
    foo2();
    
    foo2 = function() { ... }
    ```

    - 위의 code는 내부적으로 아래와 같이 작동함. 따라서 `var` 함수인 `foo2()` 와 함수선언문인 `foo()` 가 호이스팅됨
    - `var foo2` 변수에 **할당**된 함수 표현식 부분은 호이스팅 되지 않기 때문에 에러가 발생함