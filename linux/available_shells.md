# 설치되어 있는 쉘 확인

cat /etc/shells

## 사용 쉘 바꾸기
chsh 명령어

## 현재 사용중인 쉘 확인
echo $SHELL
혹은
grep {{유저명}} /etc/passwd 
