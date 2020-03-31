WeakHashMap
===

HashMap에 들어있는 Entry의 경우, Map을 제외하고 Entry의 key, value를 참조하는 변수가 없어지더라도 GC대상이 아니다. Map이 참조를 가지고 있게 되기 때문이다. 때문에 가끔 메모리 누수의 원인이 된다.

WeakHashMap은 WeakReference를 통해 참조가 없어진 Entry를 자동으로 맵에서 삭제해주는 자료구조이다.
예전에 effective java에서 처음 접했는데 한번도 사용하지 않으면서 존재조차 까먹었었다.

다시 되새김질
https://www.baeldung.com/java-weakhashmap
