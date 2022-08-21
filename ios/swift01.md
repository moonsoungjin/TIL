# 기본 문법 정리

### 이름 짓기 규칙

- Lower Camel Case
    - 맨 앞글자 소문자 표기
    - function, method, variable, constant
- Upper Camel Case
    - 맨 앞글자 대문자 표기
    - type(class, struct, enum, extension)

### 콘솔 로그 남기기

- print: 단순 문자열 출력
- dump: 인스턴스의 자세한 설명(descripion 프로터티)까지 출력 

### 문자열 보간법

- 문자열 내에 변수 또는 상수의 실질적인 값을 표현하기 위해 사용 -> \ ()

---

상수 선언 키워드 : let
변수 선언 키워드 : var

let 이름:타입 = 값
var 이름:타입 = 값
(값의 타입이 명확하다면 타입 생략 가능)

let constant: String = “차후에 변경이 불가능한 상수 let”
Var variable: String = “차후에 변경이 가능한 변수 var”

상수 선언 후에 나중에 값 할당하기
- 나중에 할당하려고 하는 상수나 변수는 타입을 꼭 명시해야 한다

let sum: Int
let inputA: Int = 100
let inputB: Int = 200

//선언 후 첫 할당
Sum = inputA + inputB

// sum = 1 // 그 이후에는 다시 값을 바꿀 수 없습니다, 오류발생

//변수도 물론 차후에 할당하는 것이 가능합니다
Var nickName: String

nickName = “sungjin”

//변수는 차후에 다시 다른 값을 할당해도 문제가 없다
nickName = “성진”
