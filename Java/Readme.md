# JVM(Java Virtual Machine)

Java는 완전한 기계어가 아닌 중간 단계의 Byte code이기 때문에 이를 해석하고 실행할 수 있는 `Stack 기반의 가상 운영체제`이다. Byte code는 모든 JVM에서 동일한 실행 결과를 보장하지만, JVM은 운영체제에 종속적이다. Java 프로그램을 기계어로 번역해서 실행해야 하기때문에 Machine의 운영체제에 맞게 설치 되어야 한다.

## JVM의 역할

- Java Application을 Class loader를 통해 읽어들이며 Java API와 함께 실행하는 것이다.
- Java 와 OS(Operating System) 간 중재자 역할을 수행하여 OS에 구애받지 않고 재사용을 가능하게 해준다.
- 메모리 관리(Garbage collection, GC)

## 실행 과정

![jvm-architecture](../Images/jvm-architecture.png)

1. 프로그램 실행 시 JVM은 OS로부터 프로그램이 필요로 하는 메모리 할당 (JVM은 이 메모리를 용도에 따라 여러 영역으로 나누어 관리)
2. Java Compiler(javac)가 Java Source Code(.java)를 읽어 Java Byte Code(.class)로 변환
3. Class Loader를 통해 class 파일들을 JVM으로 구동
4. Loading된 class 파일들은 Execution Engine을 통해 해석
5. 해석된 Byte Code는 Runtime Data Areas에 배치되어 실질적인 수행 이루어짐
   - JVM은 필요에 따라 쓰레드 동기화나 GC같은 관리작업 수행

## JVM 구성

### Class Loader

JVM내로 .class 파일을 로드하고, 링크를 통해 배치하는 작업을 수행하는 모듈이다. Runtime 시 동적으로 클래스를 로드한다. jar파일 내 저장된 클래스들을 JVM위에 탑재하고 사용하지 않는 클래스들은 메모리에서 삭재한다. 또한 Java가 동적코드이기 때문에 런타임에 참조하는 특성을 맞추어 클래스를 처음 참조 시, 해당 클래스를 로드하고 링크하는 컴파일러 역할을 수행한다.

### Execution Engine

클래스를 실행시키는 역할로 클래스 로더가 런타임 JVM내 데이터 영역에 바이트 코드를 배치시키고, 이를 실행 엔진에 의해 실행시킨다. 바이트 코드는 인간이 보기 편한 형태로 기술된 언어로, JVM내부에서 이를 기계어로 번역한다. 이때 두가지 방식(Interpreter, JIT)을 사용한다.

- Interpreter

  실행 엔진은 자바 바이트 코드를 명령어 단위로 읽어서 실행한다. 하지만 이 방식은 한줄 씩 수행하기 때문에 느리다는 인터프리터 언어의 단점을 그대로 갖고 있다.

- JIT(Just-In-Time)
  
  Interpreter 방식의 단점을 보완하기 위해 도입된 컴파일러이다. 



[More info](https://javatutorial.net/jvm-explained)
