# ChiselBench-autotest

## spec 작성법
- 빈값은 0으로 채운다
- 개수표시는 인자뒤에 -n으로 표시한다 ex)file-1 파일 한개
- Option에는 기본 명령어 옵션들이 단일 옵션으로 들어감
- Own에는 변경시킬 user랑 group이 들어감
- AddOption에는 int, string, auth, user,group이 들어감
- File or Dir는 file인지 dir인지 구분
- NewFile or NEwDir는 생성하거나 존재하지않는 file인지 dir인지 구분
- diff type은 표준출력비교는 out , ls -al 비교는 lsread, 리다이렉션은 re

Option |Own| AddOption | File or Dir | NewFile or NewDir | diff type | Ambiguity |
:------:|:------:| :---------: | :------------:|:-----------:|:-----------:|:-----------:|
(cut) -c| 0 |int-2| file-1 |0| out | 0 |
(wc) -l | 0 | 0 | file-1 |0| out | 0|
(tr) -d | 0 | string-2 |0|0|out|0|
(mkdir) -m|0| auth-1 |0|newdir-1|lsread|0|
(du) -l | 0|0 | dir-1 |0| out | 0|
(chown) -R | user-1 | 0|file-1|0|lsread|0
(chown) -R | group-1 | 0|file-1|0|lsread|0