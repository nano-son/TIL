
## Nio  Direct Byte Buffer

- nio에서 byte buffer를 크게 두가지 형태로 제공하는데, heap buffer, non-heap buffer 이렇게 구분할 수 있다. 후자가 native memory영역을 사용하는 direct buffer다.
- os는 모든 입출력 작업을 하기 위해선, 대상 내용이 반드시 native memory에 있어야한다.
- nio에서는 heap buffer를 쓰더라도 io하기 위해서 나중에 direct buffer가 필요하다. 결국 direct buffer는 필요하다.
- Furthermore, the JDK caches one or more DirectByteBuffers per thread, and by default, there is no limit on the number or size of these buffers.
- -Djdk.nio.maxCachedBufferSize 옵션을 줘서 thread당 사용할 direct buffer의 최대용량을 제한할 수 있다. 그런데 여기에는 함정이 있다. (Setting -Djdk.nio.maxCachedBufferSize doesn’t prevent allocation of a big DirectByteBuffer — it only prevents this buffer from being cached and reused. )

다이렉트 버퍼는 양날의 검이다. io 퍼포먼스를 위해서 반드시 필요하지만, 잘못 쓰면 위험하다. 

## References

- https://dzone.com/articles/troubleshooting-problems-with-native-off-heap-memo
- https://docs.oracle.com/javase/8/docs/api/java/nio/ByteBuffer.html
- https://www.javamex.com/tutorials/io/nio_buffer_performance.shtml
- https://www.evanjones.ca/java-bytebuffer-leak.html

