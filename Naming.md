# Promote Clear Usage(명확하게 사용하기)
Include all the words needed to avoid ambiguity for a person reading code where the name is used.   
>이름이 사용된 코드를 읽을 사람들을 위해 `모호하지 않도록 필요한 모든 단어를 포함합니다.`   

<br>

For example, consider a method that removes the element at a given position within a collection.   
>예를 들어, 컬렉션 내 주어진 위치에 있는 요소를 제거하는 메서드를 고려합니다.
```Swift
✅
extension List {
    public mutating func remove(at position: Index) -> Element
}

employees.remove(at: x)
```

<br>

If we were to omit the word at from the method signature, it could imply to the reader that the method searches for and removes an element equal to x, rather than using x to indicate the position of the element to remove.
>메서드 서명에서 at이라는 단어를 생략한다면, 읽는 사람에게 제거할 요소의 위치를 나타내기 위해 x를 사용했다기보다, x와 같은 요소를 검색하거나 제거한다는 의미일 수 있음을 시사합니다.
```Swift
❌
employees.remove(x) // unclear: are we removing x? (불문명: x를 제거하는가?)
```

---
Omit needless words. Every word in a name should convey salient information at the use site.
>`불필요한 단어는 생략한다.` 이름 내 모든 단어는 사용 장소에서 핵심적인 정보를 전달해야 합니다.

<br>

More words may be needed to clarify intent or disambiguate meaning, but those that are redundant with information the reader already possesses should be omitted. In particular, omit words that merely repeat type information.
>분명한 의도나 모호하지 않은 의미를 위해 더 많은 단어가 필요할 수 있지만, 읽는 사람이 이미 알고 있는 중복된 정보는 생략합니다. 특히, 타입 정보만 반복하는 단어는 생략합니다. 
```Swift
❌
public mutating func removeElement(_ member: Element) -> Element?

allViews.removeElement(cancelButton)
```

<br>

In this case, the word Element adds nothing salient at the call site. This API would be better:
>이 경우, Element 단어는 호출 장소에서 핵심적인 정보를 더하지 않습니다. 이 API 가 더 나을 수 있습니다.
```Swift
✅
public mutating func remove(_ member: Element) -> Element?

allViews.remove(cancelButton) // clearer
```

<br>

Occasionally, repeating type information is necessary to avoid ambiguity, but in general it is better to use a word that describes a parameter’s role rather than its type. See the next item for details.
>떄때로 모호함을 피하기 위해 타입 정보를 반복하는 것은 필요하지만, 일반적으로 타입보다는 매개변수의 역할을 설명하는 단어를 사용하는 것이 더 낫습니다. 자세한 내용은 다음 항목을 참조합니다.

---
Name variables, parameters, and associated types according to their roles, rather than their type constraints..
>타입 제약이 아닌 `해당 역할에 따라 변수, 매개변수, 및 연관 타입을 명명합니다.`
```Swift
❌
var string = "Hello"

protocol ViewController {
    associatedtype ViewType: View
}

class ProductionLine {
    func restock(from widgetFactory: WidgetFactory)
}
```

<br>

Repurposing a type name in this way fails to optimize clarity and expressivity. Instead, strive to choose a name that expresses the entity’s role.
>이런 방식으로 타입 이름을 고치는 것은 명확성과 표현성을 최적화하지 못합니다. 대신, 개체의 역할을 나타내는 이름을 선택하도록 노력합니다.
```Swift
✅
var greeting = "Hello"

protocol ViewController {
    associatedtype ContentView: View
}

class ProductionLine {
    func restock(from supplier: WidgetFactory)
}
```

<br>

If an associated type is so tightly bound to its protocol constraint that the protocol name is the role, avoid collision by appending Protocol to the protocol name:.
>연관 타입이 프로토콜 이름이 역할일 정도로 프로토콜 제약에 매우 밀접하게 결합되었다면, 프로토콜 이름에 Protocol을 붙여 충돌을 피합니다.
```Swift
protocol Sequence {
    associatedtype Iterator: IteratorProtocol
}

protocol IteratorProtocol {...}
```
---

Compensate for weak type information to clarify a parameter’s role..
>매개변수의 역할을 명확하게 하기 위해 `약한 타입 정보를 보완합니다.`

<br>

Especially when a parameter type is NSObject, Any, AnyObject, or a fundamental type such Int or String, type information and context at the point of use may not fully convey intent. In this example, the declaration may be clear, but the use site is vague.
>특히 매개변수 타입이 NSObject, Any, AnyObject, 또는 Int나 String 같은 기본 타입인 경우, 사용 시점에 타입 정보와 콘텍스트가 의도를 완전히 전달하지 못할 수 있습니다. 이 예제에서 선언은 명확할 수 있지만, 사용 장소가 모호합니다.
```Swift
❌
func add(_ observer: NSObject, for keyPath: String)

grid.add(self, for: graphics)  // vague
```

<br>

To restore clarity, precede each weakly typed parameter with a noun describing its role:
>명확하게 하려면, `각 약한 타입의 매개변수 앞에 그 역할을 설명하는 명사를 위치시킵니다:`
```Swift
✅
func addObserver(_ observer: NSObject, forKeyPath path: String)

grid.addObserver(self, forKeyPath: graphics) // clear
```

---
---


    