# ChiselBench-autotest

## spec 작성법
- 빈값은 0으로 채운다
- 개수표시는 인자뒤에 -n으로 표시한다 ex)file-1 파일 한개
- Option에는 기본 명령어 옵션들이 단일 옵션으로 들어감
- AddOption에는 int, string, auth, user,group이 들어감
- File or Dir는 file인지 dir인지 구분
- diff type은 표준출력비교는 out , ls -al 비교는 lsread, 리다이렉션은 re

Option | AddOption | File or Dir | diff type | Ambiguity |
:------: | :---------: | :------------:|:-----------:|:-----------:|
(cut) -c |int-2| file-1 | out | 0 |
(wc) -l  | 0 | file-1 | out | 0|
(tr) -d  | string-2 |0|out|0|
(mkdir) -m | auth-1 |newdir|lsread|0|
(du) -l | 0 | dir-1 | out | 0|
