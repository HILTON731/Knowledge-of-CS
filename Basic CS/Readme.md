# Computer Science Common Knowledge 🙂
- [Computer Science Common Knowledge 🙂](#computer-science-common-knowledge-)
- [좋은 코드란 무엇인가](#좋은-코드란-무엇인가)
- [Programming Paradigm](#programming-paradigm)
- [Procedural Programming](#procedural-programming)
  - [장단점](#장단점)
    - [장점](#장점)
    - [단점](#단점)
  - [Reference](#reference)
- [Object Oriented Programming](#object-oriented-programming)
  - [기본 구성요소](#기본-구성요소)
  - [장점](#장점-1)
  - [단점](#단점-1)
  - [OOP의 특징](#oop의-특징)
  - [OOP 설계 원칙](#oop-설계-원칙)
  - [Reference](#reference-1)
- [Overloading & Overriding](#overloading--overriding)
  - [오버로딩 (Overloading)](#오버로딩-overloading)
  - [오버라이딩 (Overriding)](#오버라이딩-overriding)
  - [Reference](#reference-2)
- [Functional Programming](#functional-programming)
  - [장점](#장점-2)
  - [단점](#단점-2)
  - [Immutable vs mutable](#immutable-vs-mutable)
  - [First-class Functions](#first-class-functions)
  - [Reactive Programming](#reactive-programming)
  - [Reference](#reference-3)
- [RESTful API](#restful-api)
  - [REST 6가지 원칙](#rest-6가지-원칙)
  - [RESTful하게 API를 다자인 한다는 것의 의미(요약)](#restful하게-api를-다자인-한다는-것의-의미요약)
  - [장점](#장점-3)
  - [단점](#단점-3)
  - [Reference](#reference-4)
- [MVC pattern](#mvc-pattern)
- [Git & GitHub](#git--github)
- [Compiler vs Interpreter](#compiler-vs-interpreter)
  - [Compiler](#compiler)
  - [Interpreter](#interpreter)
  - [Compare both](#compare-both)

[Back](https://github.com/HILTON731/Job_interview)


<br>

# 좋은 코드란 무엇인가

`좋은 코드`의 기준은 다양하며 개개인마다 각양각색이다.

- 읽기 좋은 코드
- 중복이 업슨 코드
- 테스트가 용이한 코드
- 기타

[Detail](https://jibee.io.etc/what-is-good-code/)

[Back](../Readme.md) / [Top](#computer-science-common-knowledge-)

# Programming Paradigm

- 명령형 프로그래밍(Imperative Programming): 프로그래밍의 상태와 상태를 변경시키는 구문의 관점에서 연산을 설명하는 방식으로 알고리즘을 명시하고 목표를 명시하지 않는다.
  - 절차지향 프로그래밍(Procedural Programming): 수행되어야 할 연속적인 계산 과정을 포함하는 방식
  - 객체지향 프로그래밍(Object-Oriented Programming): 객체들의 집합으로 프로그램의 상호작용을 표현
- 선언형 프로그래밍(Declarative Programming): 어떤 방법으로 해야하는지(How)를 나타내기보다 무엇(What)과 같은지를 설명하는 방식으로 알고리즘을 명시하지 않고 목표만 명시한다.
  - 함수형 프로그래밍(Functional Programming): 순수 함수를 조합하고 소프트웨어를 만드는 방식

# Procedural Programming

`절차지향 프로그래밍`(Procedural Programming)이란 순차적인 처리가 중요시 되며 프로그램 전체가 유기적으로 연결되도록 만드는 프로그래밍 기법이다. 컴퓨터 작업 처리 방식과 유사하기 때문에 객체지향 언어를 사용하는 것에 비해 빨리 처리되어 시간적으로 유리하다. 

## 장단점

### 장점

  - 컴퓨터의 처리구조와 유사해 빠른 실행 속도

### 단점
  - 유지보수가 어려움
  - 실행 순서가 고정되어 코드의 순서가 바뀌면 동일한 결과를 보장하기 어려움
  - 디버깅이 어려움

## Reference

- [절차지향 vs 객체지향](https://brownbears.tistory.com/407)

[Back](../Readme.md) / [Top](#computer-science-common-knowledge-)

# Object Oriented Programming

`객체지향 프로그래밍`(Object-Oriented Programming, OOP)은 컴퓨터 프로그래밍의 패러다임 중 하나로, 컴퓨터 프로그램을 명령어의 목록으로 보는 시각에서 벗어나 여러 개의 독립된 단위인 "객체"들의 모임으로 파악하는 것이다. 즉, <u>__프로그래밍에서 필요한 데이터를 추상화시켜 상태와 행위를 가진 객체를 만들고 그 객체들 간의 유기적인 상호작용을 통해 로직을 구성하는 프로그래밍 방법__</u>이다.


## 기본 구성요소

- 클래스(Class) 

  어떤 문제를 해결하기 위한 데이터를 만들기 위해 추상화를 거쳐 집단에 속하는 
  `상태(state)`와 `행위(behavior)`를 `속성(Field)`과 `동작(Method)`로 정의한 것이다.

    구성 멤버
  - __Field__<br>
  객체의 상태 정보를 저장하는 곳으로 변수와 선언 형태가 유사하다. 생성자와 메소드 내에서만 사용되고 생성자와 메소드가 실행 조료되면 자동 소멸된다.
  - __Constructor__<br>
  객체 생성 시 초기화를 담당한다. 클래스 이름으로 되어있고 리턴 타입이 없다.
  - __Method__<br>
  객체의 동작으로 메소드 호출 시 해당 부분이 일괄적으로 실행된다. 객체 간 데이터 전달 수단으로 사용되며 외부로부터 매개값을 받거나, 실행 후 값을 리턴 할 수 있다.

- 객체(Object)
  
  `클래스 인스턴스`라고도 하며, 물리적으로 존재하거나 추상적으로 생각할 수 있는 것 중에서 자신의 속성을 가지고 있고 다른 것과 식별 가능한 것이다. __클래스에서 정의한 것을 토대로 실제 메모리상에서 할당된 것__ 으로 실제 프로그램에서 사용되는 데이터다.

## 장점

- __코드 재사용 용이__ : 남이 만든 클래스를 가져오거나 상속을 통해 확장 가능하다.

- __유지보수가 쉬움__ : 수정해야 할 부분이 클래스 내부에 멤버 변수 혹은 메서드로 되어 해당 부분만 수정하면 된다.
- __직관적인 코드 분석 가능__

위 장점들을 관통하는 OOP의 특성은 __강한 응집력(Strong Cohesion)과 약한 결합력(Weak Coupling)을 지향__ 한다는 점이다.

## 단점
- 상대적으로 느린 처리속도
- 객체가 많을 경우 용량이 커질 수 있음
- 설계 시 많은 시간과 노력 필요

## OOP의 특징

- 캡슐화(Encapsulation)
   
  객체의 데이터에 대한 직접 접근을 방지하고, 함수를 통해서만 조작이 가능하게 하는 작업으로 __속성__ 과 __기능__ 을 하나로 묶어 `Object` 안에 정의하는 것이다. 객체 내에서 정의된 속성들은 해당 객체에서만 접근 가능하다.

- 추상화(Abstraction)
  
  객체들이 가진 공통의 특성들을 파악하고 불필요한 특성들을 제거하는 과정이다. 어떤 복잡한 프로그램을 객체로 추상화 시켜 내부 구현을 몰라도 사용자가 사용하기 쉽게 만드는 것이다.

- 상속(Inheritance)

  부모 클래스의 특징을 물려받는 것으로 자식 클래스도 부모의 속성이나 기능을 상속받아 갖게된다. 이때 자식클래스는 상속받은 속성이나 기능을 다르게 구현할 수 있으며, 다중 상속은 불가능하다.

- 다형성(Polymorphyism): 
  같은 타입이지만 실행 결과가 다양한 객체를 이용할 수 있는 성질을 말한다. 부모 클래스로부터 상속받은 메소드를 자식의 상황에 맞게 다르게 구현될 수 있는 경우에 해당한다.

- 재사용성(Recycling): 
  같은 객체를 여러 개 만들어야 하는 경우, 한 번 작성된 코드를 활용하여 동일한 객체를 만들 수 있다.

## OOP 설계 원칙

1. SRP(Single Responsibility Principle): 단일 책임 원칙

  클래스는 단 하나의 책임을 가져야 하며 클래스를 변경하는 이유는 다나 하나의 이유여야 한다.

2. OCP(Open-Closed Principle): 개방-폐쇄 원칙

  확장에는 열려있어야 하며 변경에는 닫혀있어야 한다.

3. LSP(Liskov Substitution Principle): 리스코프 치환 원칙

  상위 타입의 객체를 하위 타입의 객체로 치환해도 상위 타입을 사용하는 프로그램은 정상적으로 동작해야 한다.

4. ISP(Interface Segregation Principle): 인터페이스 분리 원칙

  인터페이스는 그 인터페이스를 사용하는 클라이언트를 기준은로 분리해야 한다.

5. DIP(Dependency Inversion Principle): 의존 역전 원칙

고수준 모듈은 저수준 모듈의 구현에 의존해서는 안된다.

## Reference

- [객체지향 프로그래밍 제대로 알고 가기](https://medium.com/amhocode/object-oriented-programming-객체지향프로그래밍-제대로-알고-가기-a864eff2d618)
- [객체지향 프로그래밍 개념 및 활용 저리](https://velog.io/@cyranocoding/객체-지향-프로그래밍OOP-Object-Oriented-Programming-개념-및-활용-정리-igjyooyc6c)

[Back](../Readme.md) / [Top](#computer-science-common-knowledge-)

# Overloading & Overriding

`Java`에서 다형성(Polymorphism)을 지원하는 방법이다.

## 오버로딩 (Overloading)
동일한 `Method`라도 매개변수만 다르면 정의하고 사용할 수 있다.
   - 동일한 `Method` 이름
   - 리턴형은 달라도 무관
   - 파라미터 개수가 다르거나, 데이터 타입이 달라야 함

## 오버라이딩 (Overriding)
상속 관계에 있는 클래스 간 같은 이름의 메소드를 정의하는 기술로 OOP의 특징인 다형성 중 하나이다.
  - Override 하는 `Method`가 부모 클래스에 있어야 함
  - 동일한 `Method`이름
  - `Method` 파라미터 개수와 타입, 리턴형이 같아야 함
  - 상위 `Method`와 동일하거나 내용이 추가되어야 함

## Reference
- [Overloading vs. Overriding](https://brunch.co.kr/@kimkm4726/2)

# Functional Programming

__함수형 프로그래밍(Functional Programming, FP)__ 은 __순수 함수(Pure function)__ 를 조합하고 __공유 상태(Shared state), 변경 가능한 데이터(Mutable data) 및 부작용(Side-effects)__ 을 피하여 소프트웨어를 만드는 프로세스다. FP는 __선언형(declarative)__ 이며 애플리케이션의 상태는 순수 함수를 통해 전달된다. 애플리케이션의 상태가 일반적으로 공유되고 객체의 메서드가 함께 배치되는 OOP와 대조된다.

## 장점

- 코드가 상대적으로 간결하다.
- 예측 가능하다.
- 테스트하기 쉽다.

## 단점

- 익숙하지 않을 경우 더 복잡할 수 있다.
- 문맥에 관련해서 입문자가 이해하기 어렵다.

## Immutable vs mutable

`Immutable`과 `mutable`의 차이에 대한 이해가 필요하다. `Immutable`이란 말 그대로 변경 불가능함을 의미한다. `Immutable`객체는 객체가 가지고 있는 값을 변경할 수 없는 객체를 의미하여 값이 변경될 경우, 새로운 객체를 생성하고 변경된 값을 주입하여 반환해야 한다. 이아 달리 `mutable`객체는 해당 객체의 값이 변경될 경우 값을 변경한다.

## First-class Functions

함수형 프로그래밍 패러다임을 따르고 있는 언어에서의 `함수(function)`는 `일급 객체(first-class citizen)`로 간주된다. 일급 객체라 함은 다음과 같다.

- 변수나 데이터 구조안에 함수를 담을 수 있어서 함수의 파라미터로 전달할 수 있고, 함수의 반환값으로 사용할 수 있다.
- 할당에 사용된 이름과 관계없이 고유한 구별이 가능하다.
- 함수를 리터럴로 바로 정의할 수 있다.

## Reactive Programming

반응형 프로그래밍(Reactive Programming)은 선언형 프로그래밍(Declarative Programming)이라고도 불리며, 명령형 프로그래밍(Imperative Programming)의 반대말이다. 또 함수형 프로그래밍 패러다임을 활용하는 것을 말한다. 반응형 프로그래밍은 기본적으로 모든 것을 스트림(Stream)으로 본다. 스트림이란 값들의 집합으로 볼 수 있으며 제공되는 함수형 메소드를 통해 데이터를 immutable하게 관리할 수 있다.

## Reference
- [함수형 프로그래밍 소개](https://medium.com/@jooyunghan/함수형-프로그래밍-소개-5998a3d66377)
- [함수형 프로그래밍이란?](https://medium.com/@lazysoul/함수형-프로그래밍이란-d881230f2a5e)

[Back](../Readme.md) / [Top](#computer-science-common-knowledge-)

# RESTful API

`REST`란, REpresentational State Transfer의 약자이다. 여기에 ~ful 이라는 형용사형 어미를 붙여 ~한 API라는 표현으로 사용된다. 즉, REST의 기본 원칙을 성실히 지킨 서비스 디자인은 'RESTful'하다라고 표현할 수 있다.

`REST`는 `Resource Oriented Architecture`로 API 설계의 중심에 자원이 있고 HTTP Method를 통해 자원을 처리하도록 설계하는 것이다.

## REST 6가지 원칙

- Uniform Interface
- Stateless
- Caching
- Client-Server
- Hierarchical System
- Code on demand

## RESTful하게 API를 다자인 한다는 것의 의미(요약)
  
1. 리소스와 행위를 명시적이고 직관적으로 분리한다.
   
   - 리소스는 URL로 표현되며, 가리키는 것은 명사로 표현되야 한다.
   - 행위는 `HTTP Method`로 표현하고, `GET(조회)`, `POST(생성)`, `PUT(기존 entity 전체 수정)`, `PATCH(기존 entity 일부 수정)`, `DELETE(삭제)`을 분명한 목적으로 사용한다.

2. Message는 Header와 Body를 명확하게 분리해서 사용한다.

  - Entity에 대한 내용은 body에 담는다.
  - 애플리케이션 서버가 행동할 판단의 근거가 되는 컨트롤 정보인 API 버전 정보, 응답받고자 하는 MIME 타입 등은 header에 담는다.
  - Header와 body는 http header와 http body로 나눌 수도 있고, http body에 들어가는 json 구조로 분리할 수 있다.

3. API 버전을 관리한다.

  - 환경은 항상 변하기 때문에 API의 signature가 변경될 수도 있음에 유의한다.
  - 특정 API를 변경할 대는 반드시 하위호환성을 보장해야 한다.

4. 서버와 클라이언트가 같은 방식을 사용해서 요청하도록 한다.

  - 브라우저는 form-data형식의 submit으로 보내고 서버에서는 json 형태로 보내는 식의 분리보다는 json으로 보내든, 둘다 form-data형식으로 보내든 하나로 통일한다.
  - URI가 플랫폼 중립적이어야 한다.

## 장점

1. Open API를 제공하기 쉽다.
2. 멀티플랫폼 지원 및 연동이 용이하다.
3. 원하는 타입으로 데이터를 주고 받을 수 있다.
4. 기존 웹 인프라(HTTP)를 그대로 사용할 수 있다.

## 단점

1. 사용할 수 있는 메소드가 4가지 밖에 없다.
2. 분산환경에는 부적합하다.
3. HTTP 통신 모델에 대해서만 지원한다.

## Reference
- [REST API 제대로 알고 사용하기](https://meetup.toast.com/posts/92)
- [바쁜 개발자들을 위한 RESTful API 논문 요약](https://blog.npcode.com/2017/03/02/바쁜-개발자들을-위한-rest-논문-요약/)
- [REST 아키텍처를 훌륭하게 적용하기 위한 몇 가지 디자인 팁](https://spoqa.github.io/2012/02/27/rest-introduction.html)

[Back](../Readme.md) / [Top](#computer-science-common-knowledge-)

# MVC pattern

[Understanding of MVC Architecture](https://asfirstalways.tistory.com/180)

[Back](../Readme.md) / [Top](#computer-science-common-knowledge-)

# Git & GitHub

[Gitflow vs GitHub flow vs GitLab flow](https://ujuc.github.io/2015/12/16/git-flow-github-flow-gitlab-flow/)

[Back](../Readme.md) / [Top](#computer-science-common-knowledge-)

# Compiler vs Interpreter

## Compiler

1. 고급 언어로 작성된 프로그램 전체를 목적 프로그램(.o)으로 번역한 후, 링킹 작업을 통해 컴퓨터에서 실행 가능한 실행 프로그램을 생성
2. 번역 실행 과정을 거쳐야 하기 때문에 번역 과정이 번거롭고 번역 시간이 오래 걸리지만, 한번 번역한 후 다시 번역하지 않아 실행 속도가 빠름
- C, Java 등 사용

## Interpreter

1. 고급 언어로 작성된 프로그램을 한 줄 단위로 받아들여 번역하고, 번역과 동시에 프로그램을 한 줄 단위로 즉시 실행시키는 프로그램
2. 프로그램이 직접 실행되므로 목적 프로그램이 생성되지 않음
3. 줄 단위로 번역, 실행되기 때문에 시분할 시스템에 유용하며 원시 프로그램의 변화에 대한 반응이 빠름
4. 번역 속도는 빠르지만 실행 시 매번 번역해야하기 때문에 실행속도는 느림
5. CPU 사용시간의 낭비가 큼
- Python, BASIC, APL 등 사용

## Compare both
구분|컴파일러|인터프리터
:---:|:---:|:---:
번역 단위|전체|행
Object file|생성|생성하지 않음
실행 속도|빠름|느림
번역 속도|느림|빠름
관련 언어|C, Java|Python, SQL, JSP

[Back](../Readme.md) / [Top](#computer-science-common-knowledge-)