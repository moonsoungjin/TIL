# 기본 문법 정리 3

- Any
    - Swift의 모든 타입을 지칭하는 키워드<br>
Var someAny: Any = 100<br>
someAny = “어떤 타입도 수용 가능합니다”<br>
someAny = 123.12
 - Any 타입에 Double 자료를 넣어두었더라도 Any는 Double 타입이 아니기 때문에 할당 할 수 없습니다. 명시적으로 타입을 변환해 주어야 합니다.<br><br>
let someDouble: Double = someAny // 컴파일 오류

- AnyObject
    - 모든 클래스 타입을 지칭하는 프로토콜<br>
class SomeClass {}<br>
var someAnyObject: AnyObject = SomeClass()<br><br>
- AnyObject는 클래스의 인스턴스만 수용 가능하기 때문에 클래스의 인스턴스가 아니면 할당할 수 없습니다<br>
someAnyObject = 123.12 // 컴파일 오류

- nil
    - 없음을 의미하는 키워드<br>
    - 다른 언의의 NULL,Null,null 등과 유사한 표현<br>
- 아래 코드에서 someAny는 Any 타입이고, someAnyObject는 AnyObject 타입이기 때문에 nil을 할달할 수 없습니다<br>
someAny = nil<br>
someAnyObject = nil <br><br>

## 컬렉션 타입

- Array
    - 멤버가 순서(인덱스)를 가진 리스트 형태의 컬렉션 타입입니다
    - 선언 및 생성(여러 리터럴 문법을 활용할 수 있어서 표현 방법이 다양함)<br>
// 빈 Int Array 생성<br>
var integers: Array<Int> = Array<Int>()<br>
// 같은 표현<br>
var integers: Array<Int> = [Int]()<br>
var integers: Array<Int> = []<br>
var integers: [Int] = Array<Int>()<br>
var integers: [Int] = [Int]()<br>
var integers: [Int] = []<br>
var integers = [Int]() <br>

integers.append(1)<br>
integers.append(100)<br>
// Int 타입이 아니므로 Array에 추가할 수 없습니다<br>
// integers.append(101.1)

print(integers) // [1, 100]

//멤버 포함 여부 확인<br>
print(integers.contains(100)) // true<br>
print(integers.contains(99)) // false

// 멤버 교체<br>
integers[0] = 99

// 멤버 삭제<br>
integers.remove(at: 0)<br>
integers.removeLast()<br>
integers.removeAll()<br>

// 멤버 수 확인<br>
print(integers.count)<br>

//인덱스를 벗어나 접근하려면 익셉션 런타임 오류 발생<br>
// integers[0]

- let을 사용하여 Array를 선언하면 불변 Array가 됩니다<br>
let immutableArray = [1, 2, 3]

// 수정이 불가능한 Array이므로 멤버를 추가하거나 삭제할 수 없습니다<br>
// immutableArray.append(4)<br>
// immutableArray.removeAll()<br>

- Dictionary 
    - 키와 값의 쌍으로 이루어진 컬렉션 타입입니다
    - 여러 리터럴 문법을 활용할 수 있어서 표현 방법이 다향합니다<br>
// Key가 String 타입이고 Value가 Any인 빈 Dictionary 생성<br>
var anyDictionary: Dictionary<String, Any> = [String: Any]()<br>
// 같은 표현<br>
// var anyDictionary: Dictionary <String, Any> = Dictionary<String, Any>()<br>
// var anyDictionary: Dictionary <String, Any> = [ : ]<br>
// var anyDictionary: [String: Any] = Dictionary<String, Any>()<br>
// var anyDictionary: [String: Any] = [String: Any]()<br>
// var anyDictionary: [String: Any] = [ : ]<br>
// var anyDictionary = [String: Any]()

// 키에 해당하는 값 할당<br>
anyDictionary[“someKey”] = “value”<br>
anyDictionary[“anotherKey”] = 100<br>

print(anyDictionary) // [“someKey”: “value”, “anotherKey”: 100]<br>

//키에 해당하는 값 변경<br>
anyDictionary[“someKey”] = “dictionary”<br>
print(anyDictionary) // [“someKey”: “dictionary”, “anoterKey”: 100]<br>

//키에 해당하는 값 제거<br>
anyDictionary.removeValue(forKey: “anotherKey”)<br>
anyDictionary[“someKey”] = nil<br>
print(anyDictionary)<br>

- let을 사용하면 Dictionary를 선언하면 불변 Dictionary<br>
let emptyDictionary: [String: String] = [:]<br>
let initalizedDictionary: [String: String] = [“name”: “yagom”, “gender”: ]<br>
// 불변 Dictionary 이므로 값 변경 불가<br>
// emptyDictionary[“key”] = “value”

- Set
    - 순서가 없고, 멤버가 유일한 것을 보장하는 컬렉션 타입 입니다<br>
// 선언과 생성<br>
var integerSet: Set<Int> = Set<Int>()<br>
integerSet.insert(1)<br>
integerSet.insert(100)<br>
integerSet.insert(99)<br>
integerSet.insert(99)<br>
integerSet.insert(99)<br>

print(integerSet) // [100, 99, 1]<br>
print(integerSet.contains(1)) // true<br>
print(integerSet.contains(2)) // false<br>

integerSet.remove(100)<br>
integerSet.removeFirst()<br>

print(integerSet.count) // 1<br>

- Set는 집합연산에 많이 활용됩니다

// Set는 집합 연산에 꽤 유용합니다<br>
let setA: Set<Int> = [1, 2, 3, 4, 5]<br>
let setB: Set<Int> = [3, 4, 5, 6, 7]<br>

// 합집합<br>
let union: Set<Int> = setA.union(setB)<br>
print(union) // [2, 4, 5, 6, 7, 3, 1]<br>

//오름차순 정렬<br>
let sortedUnion: [Int] = union.sorted()<br>
print(sortedUnion) // [1, 2, 3, 4, 5, 6, 7]<br>

//교집합<br>
let intersection: Set<Int> = setA.intersection(setB)<br>
print(intersection) // [5, 3, 4]<br>

//차집합<br>
let subtracting: Set<Int> = setA.subtracting(setB)<br>
print(subtracting) // [2, 1]
