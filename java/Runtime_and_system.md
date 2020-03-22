# Runtime, System class

java application을 만들 때 jvm에 어떠한 동작을 요구하거나 혹은 jvm의 정보를 가져올 때 어떤 경우는 Runtime을 사용하고 어떤 경우에는 System을 사용한다.
둘의 차이는 무엇인지 확인한다.
ref: https://www.java2novice.com/java_interview_questions/runtime-system-class/

### Runtime
singletone pattern으로 구현되어 있다.
final클래스는 아니지만 private 생성자로 인해 상속은 불가하다.

javadoc: https://docs.oracle.com/javase/7/docs/api/java/lang/Runtime.html

gc(), runFinalization(), exec(), exit(), load(), loadLibrary() 를 통해 jvm에 원하는 동작을 실행토록 할 수 있다.
addShutdownHook(), removeShutdownHook()으로 jvm shutdown 시 hook을 걸 수 있다.
totalMemory(), maxMemory(), availableProcessors() 로 메모리, cpu관련 정보를 얻을 수 있다.

### System
final 클래스라서 상속불가하며, private 생성자라서 객체 생성이 불가하다.
모든 메소드는 static으로 되어 있다.

javadoc: https://docs.oracle.com/javase/7/docs/api/java/lang/System.html

static 변수로 in, out, err 기본 입출력을 제공한다.
currentTimeMillis(), nanoTime() 등으로 현재 시스템의 시간을 반환한다.
getProperties(), getProperty(), setProperty() , clearProperty() 등의 메소드로 jvm property를 접근하고 조작할 수 있다.
gc(), runFinalization(), exit(), load(), loadLibrary()이 여기도 있네.. (exec는 여기 없음)
getLogger()가 있는데, 사용하는 것은 본적 없다. (보통 slf4j와 구현체를 사용하니..)



