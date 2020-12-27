## nohup and ampersand

nohup, ampersand(&) 모두 프로세스 데몬화를 위해 사용하는데, 차이는 무엇일까?

https://stackoverflow.com/questions/15595374/whats-the-difference-between-nohup-and-ampersand

nohup은 명령어 뜻 그대로 no hangup이다. SIGHUP 시그널을 캐치해서 프로세스로 전달하지 않는다.
반면, ampersand그러하지 않다. (단, 쉘이 그렇게 구성되거나 SIGHUP을 전혀 보내지 않는 경우 제외)

&를 붙이면 서브쉘을 사용해서 백그라운드에서 프로세스가  실행되는데, 현재 쉘에서 SIGHUP을 발생하면 서브쉘도 종료되기 때문에 프로세스가 죽을 수 있다.
따라서 nohup, & 를 같이 사용하는게 나아보인다.

다른 차이점으로는, &는 별도의 입출력 리다이렉션을 하지 않는 반면, nohup은 표준출력, 표준에러를 nohup.out 혹은 $HOME/nohup.out 으로 리다이렉션한다.

stackoverflow에서 확인한 정보로 신빙성은 없을 수 있다.
