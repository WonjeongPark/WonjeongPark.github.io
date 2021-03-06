---
layout: post
title:  "Object-Oriented Programming"
date:   2019-08-09
excerpt: "객체지향이란?"
image: "/images/react-logo.png"
---


# 객체 지향 (Object Oriented Programming)

## 객체 지향 프로그래밍이 뭘까?
[객체지향](https://ko.wikipedia.org/wiki/%EA%B0%9D%EC%B2%B4_%EC%A7%80%ED%96%A5_%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D)은
OOP는 컴퓨터 프로그래밍의 패러다임 중 하나로, 프로그램을 명령어의 목록으로 보는 시각에서 벗어나<br>
여러 개의 독립된 단위인 객체들의 모임으로 파악하고 하는 것이라 한다.<br>
>즉, 프로그래밍에서 필요한 데이터를 **추상화**시켜 **상태**와 **행위**를 가진 **객체**를 만들고,<br>
그 객체들간의 **유기적인 상호작용**을 통해 로직을 구성하는 프로그래밍 방법이다.<br>

## 객체 지향 vs 절차 지향
두 가지를 비교하기 위해서 대표적인 예시를 들어보자.<br>

```
자동차를 만들기 위해서는 엔진, 핸들, 바퀴, 의자, 엑셀, 브레이크 등 많은 부품이 필요하다.
기존의 절차 지향 방식의 관점에서 자동차를 만드는 방법은
엔진 -> 차체 -> 의자 -> 핸들 .. 식의 순서가 달라져서도 안되고 서로 분리되서는 안되며
하나가 고장나면 전체 기능이 멈추도록 설계 된 것과 비슷하다고 생각할 수 있다.
다른 종류의 부품으로도 대체 불가능 하다는 전제도 포함한다면 비효율적이고 비생산적이다.

객체지향의 관점이라면 자동차를 만들기 까지의 과정에서 순서는 상관 없다.
각각 독립적으로 만들어져 하나로 조립되고 각각의 기능만 잘 수행하면 된다.
하나의 부품이 고장나더라도 다른 부분은 영향 받지 않고 그저 문제가 있는 부분만 고치면 된다.
```
순차적인 처리 방식으로 프로그램 전체가 유기적으로 연결되어야 하는 경우에는 `절차 지향 방식`이 빨리 처리될 것이다.<br>

>기술이 발전함에 따라 하드웨어가 소프트웨어의 발달 속도보다 더뎌지면서 `객체 지향 언어`가 등장하고 중요해졌다.<br>

하드웨어가 같은 기능을 중복으로 연산하도록 하지 않고 모듈을 재활용하기에 처리량이 획기적으로 줄어들었기 때문이다.<br>

## 객체 지향 프로그래밍의 장, 단점
### 장점
- **코드 재사용**이 용이하다.<br>
클래스를 가져와 사용할 수 있고 상속을 통해 확장하여 사용 가능하다.

- **유지보수**가 쉽다.<br>
각각의 객체는 메시지를 주고 받고, 데이터를 처리하기에 프로그램을 유연하고, 변경이 용이하게 만든다.<br>
수정해야하는 부분이 클래스 내부에 멤버 변수나 메서드로 있기때문에 해당 부분만 수정가능하다.

- **대형프로젝트**에 적합하다.<br>
클래스 단위로 모듈화가능하므로 다수의 개발자가 협업 시 분담이 쉽다.

### 단점

- 처리속도가 상대적으로 느리다.<br>

- 객체의 수가 늘어나면 용량이 늘어난다.<br>

- 설계시 시간과 노력이 많이 필요하다.<br>

## 객체 지향 프로그래밍 키워드 5가지

1. **클래스와 인스턴스(객체)**<br>
문제해결을 위한 데이터를 만들기 위해 추상화를 거쳐 집단에 속하는 속성(attribute)과 행위(behavior)를 변수와 매서드로 정의한 것.<br>
`속성 -(추상화)-> 변수` `행위 -(추상화)-> 메서드`<br>

2. **추상화**<br>
불필요한 정보는 숨기고 중요한 정보만 표현함으로써 공통의 속성이나 기능을 묶어 이름을 붙이는 것.<br>
객체지향 관점에서 클래스를 정의하는 것.

3. **캡슐화**<br>
코드를 재수정없이 재활용하기 위해 관련된 기능과 특성을 한 곳에 모으로 분류하는 것.<br>
객체 지향 프로그래밍에서 기능과 특성의 모음을 클래스라는 캡슐에 분류해서 넣는 것이 캡슐화이다.<br>
캡슐화는 추상화와 거의 같은 개념이지만 추상화를 지원하며 보다 구체적이고 제한적이라 할 수 있다.<br>

4. **상속**<br>
부모클래스의 속성과 기능을 그대로 이어받아 사용하고, 자식클래스에서 변경이 필요한 부분만 다시 정의할 수 있는 것.<br>
다중상속은 혼란을 야기할 수 있으므로 반드시 하나만 가능하다.<br>
절차 지향 프로그래밍에서도 라이브러리를 통해 다른 소스코드를 가져와 사용하는 것이 가능하지만,<br>
수정하게되면 다른 라이브러리가 되어 동작하지 않거나 불필요한 코드를 수정해야하는 경우가 있다.<br>

5. **다형성**<br>
같은 모양의 코드가 다른 행위를 하는 것.<br>
하나의 변수, 함수 이름이 상황에 따라 다른 의미로 해석 될 수 있는 것이다.
- overriding<br>
부모 클래스에서 상속받은 메소드를 자식 클래스에서 같은 이름, 같은 반환값, 값은 인자로<br>
메소드 내의 로직들을 새롭게 정의하는 것.<br>
- overloading<br>
하나의 클래스에서 같은 이름으로 여러개의 메소드를 가지는 것.<br>
인자들의 타입이나 개수를 다르게 하면 어떤 메소드를 호출할 지 컴파일러가 알 수 있다.<br>

## 추상화
### 추상클래스
객체를 직접 생성할 수 있는 클래스 -> 실체 클래스<br>
실체 클래스들의 공통적인 속성(필드,메소드)만 뽑아내어 선언한 클래스 -> `추상클래스`<br><br><br>
`추상클래스`
> new 연산자를 사용하여 객체를 생성할 수 없다.<br>
추상 클래스와 실체 클래스는 상속관계에 놓여있다.<br>
추상 클래스가 부모이고 실체클래스는 자식으로, 실체클래스는 상속받은 속성 외에 추가적인 속성을 가질 수 있다.<br>
추상 클래스는 새로운 실체 클래스를 위한 부모 클래스 용도로만 사용된다.<br>
실체 클래스들의 필드와 메소드를 통일하여 실체 클래스 작성 시 시간을 절약할 수 있다.<br>

<br><br>

이해하기 쉬운 예제를 찾아 약간의 각색을 통해 적어본다.<br>
```
추상은 덜 구체화된 것.
객체는 상태와 행동을 가진 것.
클래스는 객체를 만들기 위한 틀.
초기화는 클래스를 이용하여 객체를 생성.

우리는 클래스를 이용하여 객체를 생성한다.
CAT클래스를 이용하여 고양이객체를 만들고 (상태와 행동), TIGER클래스를 이용하여 호랑이객체를 만든다.(상태와 행동)
그렇다면 추상클래스인 ANIMAL클래스로 어떤 객체를 만들 수 있을까?
ANIMAL객체를 만들 수 없다. 동물객체는 오답일 것이다.
동물은 상태와 행동을 가져야하는 객체의 모습을 가질 수가 없다.
불완전한 클래스를 통해 만든 객체가 객체의 모습이 아닐 때 객체 생성할 수 없도록 하는 것. 이것이 추상클래스이다.
```

`추상메소드`
> 추상메소드란 메소드의 선언부만 있고 실행 내용인 중괄호 {}가 없는 메소드이다.<br>
끝은 항상 세미콜론이 있다.<br>
추상메소드는 추상 클래스에서만 선언할 수 있다.<br>
메소드 실행 내용 {}은 추상메소드를 상속받은 실체 메소드에서 직접 작성한다.<br>
**반드시 자식클래스는 추상메소드를 재정의(Overriding)해서 실행 내용을 작성해야한다.**<br>
추상 클래스를 설계할 때, 자식 클래스가 반드시 실행해야하는 메소드를 추상 메소드로 선언하면 된다.<br>

JAVA에서는 여기에 인터페이스 개념이 동반된다.<br>
추상클래스와 비슷한 기능을 하지만 조금 더 강한(?) 경우로 <br>
추상메소드와 상수로만 이루어져 있고 다중상속이 가능하다.<br>


## 캡슐화
### 은닉성

`값이 변화하는 타이밍을 객체 스스로 알기`<br>
Cat.name = 'soonmoo'와 Cate.SetName('soonmo')의 차이는 무엇일까?<br>

캡슐화는 중요한 데이터를 보존, 보호하는 것이다.<br>
연관있는 변수와 함수를 클래스로 묶는 작업(클래스에 담는 중요한 데이터나 기능을 외부에서 접근하지 못하도록 함)<br>
Javascript에서는 기본은 public, private& protected에 앞에 `_`를 붙인다.(암묵적인 약속)<br>

```
function ExampleClass() {

//public 프로퍼티
this.프로퍼티이름 = 값;

//private/protected 프로퍼티
this._프로퍼티이름 = 값; }

// public 메소드
ExampleClass.prototype.메소드이름 = function() { ... }

// private/protected 메소드
ExampleClass.prototype._메소드이름 = function() { ... }

```

<br>

즉 캡슐화는 타인이 외부에서 조작하는 것을 대비해서<br>
특정 속성이나 메소드를 사용자가 접근 할 수 없도록 숨겨놓은 것이다.

> 자바 언어는 캡슐화된 것을 노출시킬 것인지 숨길 것인지를 결정하는 접근 제한자를 사용한다.

private, public의 노출 범위를 정해서 속성 값을 보호한다는 느낌<br>
**외부에서 접근이 가능하여 프로퍼티 값이 변경 가능하다면
클래스 외부에서 프로퍼티 값이 바뀌는 것이므로 바뀌는 시점을 알기 힘들다.**<br>
따라서 private으로 은닉한다면 값의 변화를 메소드 안에서만 처리되므로 예의주시할 수 있다.<br>
객체 스스로 자신의 소중한 데이터를 지켜야 하는 이유 => `값이 변화하는 타이밍을 객체 스스로 알게 하기 위함`<br>
유지보수성, 디버깅이 용이하고 추적이 쉽다.<br>

<br><br>

## 객체지향의 5원칙 (SOLID)
1. SRP(단일 책임의 원칙Single Responsibility Principle)
2. OCP (개방폐쇄의 원칙: Open Close Principle)
3. LSP (리스코브 치환의 원칙: The Liskov Substitution Principle)
4. ISP (인터페이스 분리의 원칙: Interface Segregation Principle)
5. DIP (의존성역전의 원칙: Dependency Inversion Principle)
