# 기본 문법 정리 2

## 기본 데이터 타입


- Bool
    - true와 false만을 값으로 가지는 타입<br>
var someBool: Bool = true<br>
someBool = false <br>
// someBool = 0 // 컴파일 오류 <br>
// someBool = 1 // 컴파일 오류 <br>

- Int, UInt
    - Int
        - 정수 타입, 현재는 기본적으로 64비트 정수형. <br>
var someInt: Int = -100 <br>
// someInt = 100.1 // 컴파일 오류 <br>

    - UInt
        - 양의 정수 타입. 현재는 기본적으로 64비트 양의 정수형 <br>
var someUInt: UInt = 100 <br>
// someUInt = -100 // 컴파일  오류 <br>
// someUInt = someInt // 컴파일 오류 <br>

- Float, Double
    - Float
        - 실수 타입, 32비트 부동소수형<br>
var someFloat: Float = 3.14<br>
someFloat = 3

    - Double
        - 실수타입, 64비트 부동소수형.<br>
var someDouble: Double = 3.14<br>
someDouble = 3<br>
// someDouble = someFloat // 컴파일오류

- Character, String
    - Character
        - 문자 타입, 유니코드 사용, 큰따옴표(“”) 사용<br>
Var someCharacter: Character = “😀”<br>
someCharacter = “🏸”<br>
someCharacter = “가”<br>
someCharacter = “A”<br>
// someCharacter = “하하하” // 컴파일 오류<br>
print(someCharacter)

- String
    - 문자열 타입, 유니코드 사용, 큰따옴표(“”)사용<br>
var someString: String = “하하하 ?”<br>
someString = someString + “웃으면 복이와요”<br>
print(someString)<br>
// someString = someCharacter // 컴파일 오류
