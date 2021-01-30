## TIMEWAIT 소켓이 많다?

그렇다면 tcp keepalive 옵션을 사용하는지 확인하자.
timewait이 많으면 높은확률로 tcp keepalive가 꺼져있다.

tcp 연결유지를 위해 연결시 3 way, 종료시 4way handshake를 하게 되는데 이 오버헤드가 클 수 있다.
time wait은 4way의 마지막 단계로써, 연결 종료를 기다리는 소켓들이 많다는 것이고 요청이 많이 들어온다면 timewait 소켓이 빠르게 늘어날 수 있다.

회피책
1. tcp keepalive를 키거나
2. tcp tw reuse를 키거나
3. 둘다 한다.


가급적 둘 다 하는게 좋다. 이 때 유의할점은 http keepalive는 tcp keepalive와 무관하다는 것이다.
http keepalive time을 높게 잡는다면 idle time이 길어질 수 있고 이는 오히려 불필요한 소켓들을 열어놓고 있을 수 있다.
그래서 http keepalive의 경우 주변 환경과 지표를 참고하여 적절한 값을 정해야한다.

하지만 그 "적절한"은 늘 어렵기 때문에 아직은 잘 모른다. 주변 서버들의 idle time out을 참고하거나 도메인 특성을 조합해서 판단해야할듯...


참고
- https://brunch.co.kr/@alden/2
- https://brunch.co.kr/@alden/9
- https://tech.kakao.com/2016/04/21/closewait-timewait/
