 # 기본 문법 정리 4

 ## 함수

 ### 함수의 선언
 - 함수선언의 기본형태
 <pre>
 <code>
    func 함수이름(매개변수1이름: 매개변수1타입, 매개변수2이름: 매개변수2타입 ...) -> 반환타입 {
        함수 구현부
        return 반환값
    }

    //예)
    sum이라는 이름을 가지고 a와 b라는 Int 타입의 매개변수를 가지며 
    Int 타입의 값을 봔환하는 함수

    func sum(a: Int, b: Int) -> Int {
        return a + b
    }
  </code>
  </pre>  

  - 반환 값이 없는 함수

  <pre>
  <code>
  func 함수이름(매개변수1이름: 매개변수1타입, 매개변수2이름: 매개변수2타입 ...) -> Void {
    함수 구현부
    return
  }

  // 예)
  func printMyname(name:String) -> Void {
    print(name)
  }
  //반환 값이 없는 겨우, 반환 타입(Void)을 생략해 줄 수 있습니다
  func printYourName(name: String) {
    print(name)
  }
  </pre>
  </code>

  - 매개변수가 없는 함수
  <pre>
  <code>
  func 함수이름() -> 반환타입 {
    함수 구현부
    return 반환값
  }
  // 예)
  func maximumIntegerValue() -> Int {
    return Int.max
  }
  </pre>
  </code>

  - 매개변수와 반환값이 없는 함수

  <pre>
  <code>
  func 함수이름() -> Void {
    함수 구현부
    return
  }
  // 함수 구현이 짧은 경우
  // 가독성을 해치지 않는 범위에서 
  // 줄바꿈을 하지 않고 한 줄에 표현해도 무관합니다
  fcun hello() -> {print("hello")}
  // 반환 값이 없는 경우, 반환 타입(Void)을 생략해 줄 수 있습니다
  func 함수 이름() {
    함수 구현부
    return
  }
  func bye() {print("bye")}
  </pre>
  </code>

  - 함수의 호출
    - sum(a: 3, b: 5) // 8
    - printMyName(name: "sungjin") // sungjin
    - printYourName(name: "moon") // moon
    - maximumIntegerValue() // Int의 최댓값
    - hello() // hello
    - bye() // bye

## 고급 함수

- 매개변수 기본 값
  - 매개변수에 기본적으로 전달될 값을 미리 지정할 수 있습니다
  - 기본값을 갖는 매개변수는 매개변수 목록 중에 뒤쪽에 위치하는 것이 좋습니다

<pre>
<code>
func 함수이름(매개변수1이름: 매개변수1타입, 매개변수2이름: 매개변수2타입 = 매개변수 기본값 ...) -> 반환타입 {
  함수 구현부
  return 반환값
}

func greeting(friend: String, me: String="sungjin") {
  print("Hello \(friend)! I`m \(me)")
}

// 매개변수 기본값을 가지는 매개변수는 호출시 생략할 수 있습니다
greeting(friend: "haha") // Hello haha! I`m sungjin
greeting(friend: "john", me: "eric") // Hello john! I`m eric
</pre>
</code>

- 전달인자 레이블
  - 함수를 호출할 때 함수 사용자의 입장에서 매개변수의 역할을 좀 더 명확하게 표현하고자 할 때 사용합니다

<pre>
<code>
func 함수이름(전달인자 레이블 매개변수1이름: 매개변수1타입, 전달인자 레이블 매개변수2이름: 매개변수2타입 ...) -> 반환타입 {
  함수 구현부
  return 
}

// 함수 내부에서 전달인자르 사용할 때에는 매개변수 이름을 사용합니다 
func greeting(to friend: String, from me: String) {
  pring("Hello \(friend)! I`m \(me)")
}

// 함수를 호출할 때에느 전달인자 레이블을 사용해야 합니다
greeting(to: "hana", from: "sungjin") // Hello hana! I`m sungjin
</pre>
</code>

- 가변 매개변수
  - 전달 받을 값의 개수를 알기 어려울때 사용할 수 있습니다
  - swift버전 5.4 미만에서는 함수당 하나의 가변 매개변수만 가질 수 있습니다(5.4 버전 부터 여러개 가능)

<pre>
<code>
func 함수이름(매개변수1이름: 매개변수1타입 , 전달인자 레이블 매개변수2 이름: 매개변수2타입...) {
  함수 구현부
  return
}

func sayHelloToFriends(me: String, friends: String...) -> String {
  return "Hello \(friends)! I`m \(me)!"
}
print(sayHelloToFriends(me: "sungjin", friends: "hana", "eric", "wing")) // Hello ["hana", "eric", "wing"]! I`m sungjin!

print(sayHelloToFriends(me: "sungjin")) // Hello []! I`m sungjin!
</pre>
</code><br>

## 데이터 타입으로서의 함수

- 스위프트는 함수형 프로그래밍 패러다임을 포함하는 다중 패러다임 언어이므로 스위프트의 함수는 일급객체입니다. 그래서 함수를 변수, 상수 등에 할당이 가능하고 매개변수를 통해 전달할 수도 있습니다
<br><br>

- 함수의 타입표현
  - 반환타입을 생략할 수 없습니다
  - (매개변수1타입, 매개변수2타입 ...) -> 반환타입
<br><br>
- 함수타입 사용
<pre>
<code>
var someFunction: (String, String) -> Void = greeting(to:from:)
someFunction("eric","sungjin") // Hello eric! I`m sungjin

someFunction = greeting(friend:me:)
someFunction("eric","sungjin") // Hello eric! I`m sungjin

// 타입이 다른 함수는 할당할 수 없습니다 - 컴파일 오류 발생
// someFunction = sayHelloToFriends(me: friends:)

func runAnother(function: (String, String) -> Void) {
  function("jenny", "mike")
}

// Hello jenny! I`m mike
runAnother(function: greeting(friend:me))

// Hello jenny! I`m mike
runAnother(function: someFunction)
</pre>
</code>