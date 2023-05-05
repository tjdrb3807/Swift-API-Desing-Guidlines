이 문서는 API Desing Guidelines 문서의 번역본이다.

# Fundamentals
Clarity at the point of use is your most important goal.   
Entities such as methods and properties are declared only once but used repeatedly.     
Design APIs to make those uses clear and concise.    
When evaluating a design, reading a declaration is seldom sufficient; always examine a use case to make sure it looks clear in context.

<br>

>API 설계의 가장 중요한 목적은 `사용하는 시점에서의 명료성`이다.   
메서드나 프로퍼티와 같은 개체는 한 번 선언해두면 반복적으로 사용이 가능하다.    
API는 이러한 개체들을 명확하고 간결하게 사용할 수 있도록 설계해야한다.   
API 설계를 제대로 하였는지 평가할 때는 코드의 선언부를 읽는 것만으로는 충분하지 않다.   
항상 문맥에 알맞도록 명확하게 설계하였는지 실질적인 사용 예시를 통해 확인해보아야한다.   

<br>
<br>
<br>

Clarity is more important than brevity.   
Although Swift code can be compact, it is a non-goal to enable the smallest possible code with the fewest characters.   
Brevity in Swift code, where it occurs, is a side-effect of the strong type system and features that naturally reduce boilerplate.

<br>

>`명료성은 간결성보다 더 중요하다.`   
Swift 코드를 간결하게 작성할 수 있지만, 단순히 몇개의 문자들만 사용하여 가장 적은 코드를 작성하는 것이 목표가 아니다.   
Swift에서 간결성은 타입 시스템의 부수효과이고 반복되는 인용구를 자연스럽게 줄일 수 있는 기능이다.   

<br>
<br>
<br>

Write a documentation comment for every declaration.    
Insights gained by writing documentation can have a profound impact on your design, so don’t put it off.

<br>

>`모든 선언문에 문서 주석을 작성한다.`   
주석을 작성하면서 얻은 통창력은 당신의 API 설계에 엄청난 영향을 줄 수 있다.   
그러니 미루지 말고 주석을 작성하라.   

<br>
<br>
<br>

If you are having trouble describing your API’s functionality in simple terms, you may have designed the wrong API.

<br>

>만약 당신이 API 기능을 간단한 용어로 설명하는 게 어렵다면, 잘못된 API를 설계했을 수도 있다. 

<br>
<br>
<br>

Use Swift’s dialect of Markdown.

<br>

>`Swift에서 지원하는 마크다운 형식을 이용하라.`

<br>
<br>
<br>

Begin with a summary that describes the entity being declared.   
Often, an API can be completely understood from its declaration and its summary.

<br>

>선언된 개체를 설명하는 요약부터 시작해라.   
간혹, API는 선언부와 요약을 읽는 것만으로도 이해가 되기도 한다.   

```Swift
/// Return a "view" of 'self' containing the same elements in
/// reverse order.
/// 동인한 요소들을 포함하는 'self'의 "view"를 역순으로 반환.
func reversed() -> ReverseCollection
```

<br>
<br>
<br>

Focus on the summary; it’s the most important part.    
Many excellent documentation comments consist of nothing more than a great summary.

<br>

>`요약에 초점을 맞춰라.` 요약은 정말 중요한 부분이다.    
좋은 문서 주석들은 훌륭한 요약으로 이루어져 있다.   

<br>
<br>
<br>

Use a single sentence fragment if possible, ending with a period.    
Do not use a complete sentence.

<br>

>`가능하다면, 한 문장 구성 단위(구, 절)를 사용하고 끝에 마침표로 끝내라.`   
완전한 문장으로 사용하는 것은 지양한다.

<br>
<br>
<br>

Describe what a function or method does and what it returns, omitting null effects and Void returns:

<br>

>`함수 또는 메서드가 하는 일이 무엇이고, 어떤 것을 반환하는지 설명하고` null 효과와 Void 반환에 대한 설명은 생량하라.

```Swift
/// Inserts 'newHead' at the beginning of 'self'
/// 'self'의 시작부분에 'newHead' 삽입
mutating func prepend(_ newHead: Int)

/// Return a 'List' containing 'head' followed by the elements
/// of 'self'
/// 'self'의 요소에 있는 'head'가 포함된 'List' 반환
func prepending(_ head: Element) -> List

/// Removes and returns the first element of 'self' if non-empty;
/// return 'nil' otherwise.
/// 비어있지 않다면 'self'의 첫 번째 요소를 반환 및 제거하고, 비어 있다면 'nil' 반환
mutating func popFitst() -> Element?
```









