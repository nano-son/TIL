## How Class object can return URL based resource (Class::getResource)

Class 객체는 멤버 변수로 classLoader를 가지고 있다. 만약 bootstrap classloader에 의해서 로딩된 클래스라면 classLoader == null 인데,
이 때는 ClassLoader.getSystemResource를 통해서 resource를 찾아서 반환한다. (이 때는 내부적으로 system class loader가 사용된다)

class loader에도 종류가 많은데 공부해야지..
