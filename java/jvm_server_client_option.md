# JVM SERVER, CLIENT OPTION
====
일반적으로 서버와 클라이언트의 사용성은 다르다.
클라이언트는 사용자의 요구에 빠르게 반응해야하며 가급적 가벼워야한다.
서버는 오랜시간 구동되면서 많은 요청을 처리해야한다.

이러한 사용성을 인지하여 jvm을 server용 혹은 client용으로 구동시킬 수 있다.

server용 jvm실행
> java -server ~~~

client용 jvm실행
> java -client ~~~

무엇이 다른걸까?
간단히 말하면 컴파일러의 동작 방식이 다르다.

서버는 bootstrap time 보다 전반적인 response time이 더 중요하다. 그래서 시간이 지날 수록 정교하게 최적화되어 성능을 끌어올린다.

반면에 클라이언트는 bootstrap 즉시 사용자의 요청을 처리할 수 있어야하기 때문에, 빨리 기동되는것에 최적화되어 있다.

런타임에 최적화 방식이 다르다? 무엇이 그 역할을 하는걸까?
바로 JIT compiler이다. JIT compiler는 두가지 종류가 있다. server용, client용.
용도에 따라 최적화 방식이 다르다.
자세한 내용은 따로 공부하자.

java -version을 통해 디폴트 설정을 확인할 수도 있다.
```
openjdk version "11.0.2" 2019-01-15
OpenJDK Runtime Environment 18.9 (build 11.0.2+9)
OpenJDK 64-Bit Server VM 18.9 (build 11.0.2+9, mixed mode)
```
마지막 줄에 Server VM이라고 적혀있다. 디폴트로 server용으로 jvm이 구동된다.

디폴트 설정은 java home 경로 하위에 존재하는 jvm.cfg를 통해서 설정할 수 있다.
```
-server KNOWN
-client IGNORE
```

이렇게 설정되어 있기 때문에 Server VM으로 보여진 것이다.


64비트 운영체제에서는 디폴트가 Server 용이라고 한다.

### Reference
> https://stackoverflow.com/questions/198577/real-differences-between-java-server-and-java-client


