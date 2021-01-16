# Computer Science Common Knowledge

- [Computer Science Common Knowledge](#computer-science-common-knowledge)
  - [좋은 코드란 무엇인가](#좋은-코드란-무엇인가)
  - [Object Oriented Programming](#object-oriented-programming)
    - [기본 구성요소](#기본-구성요소)
    - [장점](#장점)
    - [단점](#단점)
    - [OOP의 특징](#oop의-특징)
  - [JVM(Java Virtual Machine)](#jvmjava-virtual-machine)
    - [JVM의 역할](#jvm의-역할)
    - [실행 과정](#실행-과정)
  - [Overloading & Overriding](#overloading--overriding)

[Back](https://github.com/HILTON731/Job_interview)

<br>

## 좋은 코드란 무엇인가

`좋은 코드`의 기준은 다양하며 개개인마다 각양각색이다.

- 읽기 좋은 코드
- 중복이 업슨 코드
- 테스트가 용이한 코드
- 기타

[Detail](https://jibee.io.etc/what-is-good-code/)

## Object Oriented Programming

`객체지향 프로그래밍`(Object-Oriented Programming, OOP)은 컴퓨터 프로그래밍의 패러다임 중 하나로, 컴퓨터 프로그램을 명령어의 목록으로 보는 시각에서 벗어나 여러 개의 독립된 단위인 "객체"들의 모임으로 파악하는 것이다. 즉, <u>__프로그래밍에서 필요한 데이터를 추상화시켜 상태와 행위를 가진 객체를 만들고 그 객체들 간의 유기적인 상호작용을 통해 로직을 구성하는 프로그래밍 방법__</u>이다.


### 기본 구성요소

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

### 장점

- __코드 재사용 용이__ : 남이 만든 클래스를 가져오거나 상속을 통해 확장 가능하다.

- __유지보수가 쉬움__ : 수정해야 할 부분이 클래스 내부에 멤버 변수 혹은 메서드로 되어 해당 부분만 수정하면 된다.
- __직관적인 코드 분석 가능__

위 장점들을 관통하는 OOP의 특성은 __강한 응집력(Strong Cohesion)과 약한 결합력(Weak Coupling)을 지향__ 한다는 점이다.

### 단점

- 상대적으로 느린 처리속도
- 객체가 많을 경우 용량이 커질 수 있음
- 설계 시 많은 시간과 노력 필요

### OOP의 특징

- 캡슐화(Encapsulation): 
  객체의 데이터에 대한 직접 접근을 방지하고, 함수를 통해서만 조작이 가능하게 하는 작업으로 __속성__ 과 __기능__ 을 하나로 묶어 `Object` 안에 정의하는 것이다. 객체 내에서 정의된 속성들은 해당 객체에서만 접근 가능하다.

- 추상화(Abstraction): 
  객체들이 가진 공통의 특성들을 파악하고 불필요한 특성들을 제거하는 과정이다. 어떤 복잡한 프로그램을 객체로 추상화 시켜 내부 구현을 몰라도 사용자가 사용하기 쉽게 만드는 것이다.

- 상속a(Inheritance): 
  부모 클래스의 특징을 물려받는 것으로 자식 클래스도 부모의 속성이나 기능을 상속받아 갖게된다. 이때 자식클래스는 상속받은 속성이나 기능을 다르게 구현할 수 있으며, 다중 상속은 불가능하다.

- 다형성(Polymorphyism): 
  같은 타입이지만 실행 결과가 다양한 객체를 이용할 수 있는 성질을 말한다. 부모 클래스로부터 상속받은 메소드를 자식의 상황에 맞게 다르게 구현될 수 있는 경우에 해당한다.

- 재사용성(Recycling): 
  같은 객체를 여러 개 만들어야 하는 경우, 한 번 작성된 코드를 활용하여 동일한 객체를 만들 수 있다.

## JVM(Java Virtual Machine)

Java는 완전한 기계어가 아닌 중간 단계의 Byte code이기 때문에 이를 해석하고 실행할 수 있는 `Stack 기반의 가상 운영체제`이다. Byte code는 모든 JVM에서 동일한 실행 결과를 보장하지만, JVM은 운영체제에 종속적이다. Java 프로그램을 기계어로 번역해서 실행해야 하기때문에 Machine의 운영체제에 맞게 설치 되어야 한다.

### JVM의 역할

- Java Application을 Class loader를 통해 읽어들이며 Java API와 함께 실행하는 것이다.
- Java 와 OS(Operating System) 간 중재자 역할을 수행하여 OS에 구애받지 않고 재사용을 가능하게 해준다.
- 메모리 관리(Garbage collection, GC)

### 실행 과정

![jvm-architecture](../Images/jvm-architecture.png)

1. 프로그램 실행 시 JVM은 OS로부터 프로그램이 필요로 하는 메모리 할당
2. Java Compiler(javac)가 Java Source Code(.java)를 읽어 Java Byte Code(.class)로 변환
3. Class Loader를 통해 class 파일들을 JVM으로 구동
4. Loading된 class 파일들은 Execution Engine을 통해 해석
5. 해석된 Byte Code는 Runtime Data Areas에 배치되어 실질적인 수행 이루어짐
   - JVM은 필요에 따라 쓰레드 동기화나 GC같은 관리작업 수행



## Overloading & Overriding

`Java`에서 다형성(Polymorphism)을 지원하는 방법이다.

- 오버로딩 (Overloading): 동일한 `Method`라도 매개변수만 다르면 정의하고 사용할 수 있다.
   - 동일한 `Method` 이름
   - 리턴형은 달라도 무관
   - 파라미터 개수가 다르거나, 데이터 타입이 달라야 함

- 오버라이딩 (Overriding): 상속 관계에 있는 클래스 간 같은 이름의 메소드를 정의하는 기술로 OOP의 특징인 다형성 중 하나이다.
  - Override 하는 `Method`가 부모 클래스에 있어야 함
  - 동일한 `Method`이름
  - `Method` 파라미터 개수와 타입, 리턴형이 같아야 함
  - 상위 `Method`와 동일하거나 내용이 추가되어야 함
