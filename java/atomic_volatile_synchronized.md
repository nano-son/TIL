atomic, volatile and synchronized
===

동기화란 무엇인가를 먼저 알아보자.
1. 배타적 실행
2. 가시성 확보

이 둘을 만족하면 동기화를 만족한 것이다.
(자세한 설명은 이펙티브 자바 동시성 챕터 참고)

### Atomic
atomic은 쉽게 말해 읽고 쓸때 한번에(원큐에) 끝나는가 이다.

자바는 기본적으로 4바이트의 read/write는 원자성을 보장한다. 
하지만 long, double과 같은 8바이트의 자료형에 대해서는 원자성을 보장하지 않는다.
2번만에 read/write하는 것이다.

이를 해결하기 위해 java.util.concurrent.atomic 패키지 하위의 AtomicLong과 같은 클래스를 활용하거나,
volatile을 활용한다.

### volatile
volatile은 동기화의 조건 중 가시성 확보를 지원한다. (배타적 실행은 ㄴㄴ)
volatile키워드는 변수에 사용하는 것으로, 사용시 read/write를 메모리로부터 하게 된다 (아니면 일반적으로 cpu cache를 사용하게 되기 때문에 변화에 대해서 메모리에 적용되지 않고 다른 쓰레드가 변화를 감지못할 수 있다)

volatile을 사용하게 되면 long, double에 대해서 원자성을 보장할 수 있다.

https://stackoverflow.com/a/3038233
https://docs.oracle.com/javase/specs/jls/se7/html/jls-17.html#jls-17.7

### synchronized
synchronized는 메소드 혹은 코드 블럭에 적용하여 동기화를 이뤄낸다.
해당 블럭을 실행하는 동안 다른 쓰레드의 접근을 막고(배타적 실행), 가시성을 확보한다.

http://gee.cs.oswego.edu/dl/cpj/jmm.html
(In essence, releasing a lock forces a flush of all writes from working memory employed by the thread, and acquiring a lock forces a (re)load of the values of accessible fields. While lock actions provide exclusion only for the operations performed within a synchronized method or block, these memory effects are defined to cover all fields used by the thread performing the action.)

### 결론
- 배타적 실행을 확보하기 위해서는 lock이 필요하다 (synchronized or java.util.concurrent.locks 패키지 하위의 lock 사용)

- 가시성 확보를 위해서는 synchronized 혹은 volatile이 필요
(java.util.concurrent.locks 의 클래스들이 가시성까지 확보해주는지는 아직 모르겠음)


