Chunked Response
=====
(잘못알고 있을 수도 있음)
동적 데이터를 생성해서 http응답을 내보낼 때 데이터 생성이 길어지면 필연적으로 응답이 지연된다.

만약 동적 html 내부에 동적 데이터 두개 포함하는데 각 데이터를 생성해내는데 200ms가 걸린다면 클라이언트는 최소 400ms를 기다려야한다.

물론 여기까지는 데이터를 모두 만들어서 하나의 http응답으로 준다는 가정이 존재.

이를 개선하고자 chunked reponse가 나옴.

http 1.1부터 등장한 Chunked transfer encoding은 데이 스트림 메카니즘이다.
In chunked transfer encoding, the data stream is divided into a series of non-overlapping "chunks". The chunks are sent out and received independently of one another. No knowledge of the data stream outside the currently-being-processed chunk is necessary for both the sender and the receiver at any given time.

Each chunk is preceded by its size in bytes. The transmission ends when a zero-length chunk is received. The chunked keyword in the Transfer-Encoding header is used to indicate chunked transfer.

An early form of the chunked transfer encoding was proposed in 1994.[1] Chunked transfer encoding is not supported in HTTP/2, which provides its own mechanisms for data streaming.

주어가 정확히 기억안나는데, (라이브러라인가..) content-length가 없으면 자동으로 청크로 인식한다고 들었다..

ref: https://en.wikipedia.org/wiki/Chunked_transfer_encoding
