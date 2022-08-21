# 기본 문법 정리 5

## 조건문

### if-else 구문 
- if-else 구문의 기본 형태
    - if만 단독적으로 사용해도 되고, else if, else와 조합해서 사용 가능합니다
    - if 뒤의 조건 값에는 Bool 타입의 값만 위치해야 하며, 조건 값을 감싸는 소괄호는 선택사항 입니다

<pre>
<code>
if 조건 {
    실행 구문
}
else if {
    실행 구문
}
else {
    실행 구문
}

예)
let someInteger = 100

if someInteger < 100 {
    print("100 미만")
}
else if someInteger > 100 {
    print("100 초과")
}
else {
    print("100")
}
// 100

// 스위프트의 조건에는 항상 Bool 타입이 들어와야 합니다
// someInteger는 Bool 타입이 아닌 Int 타입이기 때문에
// 컴파일 오류가 발생합니다
// if someInteger {}
</pre>
</code>

### switch 구문

 - 스위프트의 switch 구문은 다른 언어에 비해 굉장히 강력한 힘을 발휘합니다.
 - 기본적으로 사용하던 정수타입의 값만 비교하는 것이 아니라 대부분의 스위프트 기본 타입을 지원하며, 다양한 패턴과도 응용이 가능합니다.
 - 각각의 case내부에는 실행가능한 코드가 반드시 위치해야 합니다
 - 매우 한정적인 값(ex. enum의 case 등)이 비교값이 아닌 한 default 구문은 반드시 작성해야 합니다
 - 명시적 break를 하지 않아도 자동으로 case 마다 break 됩니다
 - fallthrough 키워드를 사용하며 break를 무시할 수 있습니다
 - 쉼표(,)를 사용하여 하나의 case에 여러 패턴을 명시할 수 있습니다

 <pre>
 <code>
 switch 구문의 기본 형태

 switch 비교값 {
    case 패턴:
        실행 구문
    default:
        실행 구문
 }

 예)
 switch 구문의 사용
 // 범위 연산자를 활용하면 더욱 쉽고 유용합니다
 switch someInteger {
    case 0:
        print("zero")
    case 1..< 100:
        print("1~99")
    case 100:
        print("100")
    case 101...Int.max:
        print("over 100")
    default:
        print("unknown")
 }
 // 100

 // 정수 외의 대부분의 기본 타입을 사용할 수 있습니다
 switch "sungjin" {
    case "jake":
        print("jake")
    case "mina":
        print("mina")
    case "sungjin":
        print("sungjin!!")
    default:
        print("unknown")
 }
 // sungjin!!
 </pre>
 </code>