# git lfs (large file storage)

ref: https://devlog.github.io/git-lfs/2015/12/09/git-lfs.html
ref: https://git-lfs.github.com/

git을 사용하면서 버전 관리가 무척 쉽고 간단해졌다. 하지만 git 입장에서도 그럴까?
용량이 작은 소스코드 같은경우는 큰 문제가 되지 않지만 용량이 큰 비디오, 오디오, 이미지 등은 git입장에서 관리하기 버거울 수 있다.

git을 사용하게 되면 현재 파일 뿐만 아니라 파일들의 full change history를 모두 가지고 있어야한다. 거대한 파일이 변경 될 때 마다 레파지토리의 크기는 점점 커져만간다.

이러한 문제를 해결하기 위해 등장한 것이 lfs이다. large file storage의 약자로, 용량이 큰 파일을 여기에 저장한다는 것이다.
그러면 git repository에는 무엇이 저장되는가?

대용량 파일을 그대로 저장하지 않고 저장되어 있는 곳을 가리키도록 text pointer를 저장한다. (git repository에)

lfs로 트래킹하도록 설정하는것도 매우 간단하다고 한다.
또한 git flow를 해치지 않는다고 하는데, 와닿지는 않지만 이래야만 편하게 사용할 수 있을 것 같다.


