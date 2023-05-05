# Fundamentals(핵심 개념)

<br>

Clarity at the point of use is your most important goal. Entities such as methods and properties are declared only once but used repeatedly. Design APIs to make those uses clear and concise. When evaluating a design, reading a declaration is seldom sufficient; always examine a use case to make sure it looks clear in context.

>API 설계의 가장 중요한 목적은 `사용하는 시점에서의 명료성`입니다. 메서드나 프로퍼티와 같은 개체는 한 번 선언해두면 반복적으로 사용이 가능합니다. API는 이러한 개체들을 명확하고 간결하게 사용할 수 있도록 설계해야합니다. API 설계를 제대로 하였는지 평가할 때는 코드의 선언부를 읽는 것만으로는 충분하지 않습니다. 항상 문맥에 알맞도록 명확하게 설계하였는지 실질적인 사용 예시를 통해 확인해보아야합니다.   

<br>
<br>

Clarity is more important than brevity. Although Swift code can be compact, it is a non-goal to enable the smallest possible code with the fewest characters. Brevity in Swift code, where it occurs, is a side-effect of the strong type system and features that naturally reduce boilerplate.

>`명료성은 간결성보다 더 중요합니다.` Swift 코드를 간결하게 작성할 수 있지만, 단순히 몇개의 문자들만 사용하여 가장 적은 코드를 작성하는 것이 목표가 아닙니다. Swift에서 간결성은 강력한 타입 시스템의 부수효과이고 반복되는 인용구를 자연스럽게 줄일 수 있는 기능입니다.

<br>
<br>

Write a documentation comment for every declaration. Insights gained by writing documentation can have a profound impact on your design, so don’t put it off.

>`모든 선언문에 문저 주석을 작성합니다.` 주석을 작성하면서 얻은 통창력은 당신의 API 설계에 엄청난 영향을 줄 수 있습니다. 그러니 미루지 말고 주석을 작성하세요.
