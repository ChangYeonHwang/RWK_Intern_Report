Day 2 - Linux 명령어
---
Linux command를 실습하고 각각의 기능에 대해 보고서를 제출하세요

+ Basic Shell Commands
+ Shell Script - Basic Concepts; 기본 문법 및 작성 방법
+ Vim 사용 방법

📕Basic Shell Commands
---
명령어 이름|설명
---|---
'cd'|현재 디렉토리 위치를 다른 위치로 변경 (Change Directory)
'ls'|현재 위치한 디렉토리에 있는 폴더와 파일 확인할 때 사용 (List)
'mv'|파일을 다른 디렉토리 위치로 이동시킬 때, 파일 이름을 변경할 때 사용 (Move)
'cp'|파일이나 디렉토리를 원하는 곳에 원하는 이름으로 복사 (Copy)
'cat'|두 개 이상의 파일을 연결해서 출력할 때 사용 (Concatenate)
'less'|파일 내용을 확인하는 명령어로 한 번에 보여지는 만큼만 새로 출력을 해주나 파일 수정은 불가
'tail'|파일의 마지막 행을 기준으로 지정한 행까지의 파일 내용 일부를 출력, 기본적으로 10개의 행을 보여준다
'nohup'|터미널을 종료해도 프로그램이 백그라운드에서 계속 실행되도록 하는 명령어
'rm'|파일과 디렉토리 삭제에 사용되는 명령어 (Remove)
'clear'|console에 있는 명령어를 모두 지움
'pwd'|현재 위치한 디렉토리를 출력 (Print Working Directory)
'chown'|파일들은 Onwer, Group에 속해있는데 이러한 Owner 또는 Group을 변경하는 명령어 (Change Owner)
'chmod'|해당 파일이나 디렉토리의 퍼미션(허용 권한)을 수정할 수 있는 명령어 [chmod 설명 블로그](https://recipes4dev.tistory.com/175)
'grep'|파일 내에서 지정한 '정규 표현식'의 패턴을 가진 문자열을 찾은 후, 해당 문자열을 출력[](https://velog.io/@devmin/TIL-%EC%A0%95%EA%B7%9C%ED%91%9C%ED%98%84%EC%8B%9D-%EC%95%8C%EC%95%84%EA%B0%80%EA%B8%B0-s8k1vs4j8y)
'history'|이전에 사용된 명령어 이력을 행 넘버와 같이 보여준다
'ps'|현재 작동하는 프로세스의 목록을 출력, 뒤에 붙는 옵션에 따라 출력되는 값이 달라진다 (Process Status)
'man', 'tldr'|다른 명령어를 설명해주지만, 내용이 길어서 부분만 출력하는 tldr을 쓰기도 함 (tldr은 따로 설치해야 함)

---

💻명령어 설명 및 실습코드 예시
---

🔎cd와 관련된 명령어

```
cd <Directory Name>  //가고자 하는 디렉토리로 이동
cd.  //현재 디렉토리 확인
cd..  //상위 디렉토리로 이동
cd /   //root, 최상위 디렉토리로 이동
cd $ 변수 이름  //변수 저장된 경로로 이동
cd ~  //사용자 디렉토리로 이동
cd $Home  //사용자 디렉토리로 이동
cd  //사용자 디렉토리로 이동
cd ~계정 이름  //입력한 사용자의 home 디렉토리로 이동
cd-  // 이전 경로로 이동
```

⌛cd 실습 코드 예시

```
# hcy12356@DESKTOP-A7B9I01:~$
cd RedwoodK
cd .
//RedwoodK 디렉토리로 이동 및 결과 확인

# hcy12356@DESKTOP-A7B9I01:~/RedwoodK$
cd practice
cd .
//RedwoodK의 하위 디렉토리인 practice로 이동 및 결과 확인

# hcy12356@DESKTOP-A7B9I01:~/RedwoodK/practice$
cd ..
cd .
//상위 디렉토리인 RedwoodK로 이동 및 결과 확인

# hcy12356@DESKTOP-A7B9I01:~/RedwoodK$
```

🔎ls와 관련된 자주 사용되는 명령어

```
ls //현재 디렉토리에 속한 파일 및 디렉토리를 출력해준다

⌛ls 실습 코드 예시

# hcy12356@DESKTOP-A7B9I01:~/RedwoodK$ ls
# README.md  day1-github구성.md  day2-linux명령어.md  practice

ls -a //숨김 파일, 및 디렉토리까지 포함한 모든 파일 형식을 출력 (all)
ls -h //사용자가 보기 좋은 형태로 각 파일들의 용량들을 단위로 표시 (human)
ls -l //리스트가 나열될 때 자세한 내용-권한, 소유자, 수정일자 등-을 출력 (long)
ls -r //파일 리스트의 출력을 거꾸로 한다 (reverse)
ls -S //출력 형식을 바꾸어, 파일의 용량 크기 순으로 리스트를 출력 
ls -t //출력 형식을 바꾸어, 가장 최근에 수정한 파일 순으로 리스트를 출력

ls는 위와 같은 명령어를 조합해서 쓸 수 있다
ls -h -al //K, M, G 단위의 파일크기를 사용하여(h) 사람에게 보기 좋게 모든 파일의 여러 정보를 표시
```

🔎mv와 관련된 자주 사용되는 명령어

```
mv <원본 파일명> <옮기고 싶은 디렉토리명>  //해당 디렉토리로 파일 이동
mv <원본 파일명> <바꾸고 싶은 파일명>  //원본 파일 이름 변경
mv <원본 디렉토리명> <옮기고 싶은 디렉토리명>  //해당 디렉토리로 디렉토리 이동
mv <원본 디렉토리명> <바꾸고 싶은 디렉토리명>  //원본 디렉토리 이름 변경
```

⌛mv 실습 코드 예시

```
# hcy12356@DESKTOP-A7B9I01:~/RedwoodK/$ mv_test.txt image
# cd image
# hcy12356@DESKTOP-A7B9I01:~/RedwoodK/image$ ls
# ubuntu-install.jpg  ubuntu-terminal.png Wsl2-install.jpg  mv_test.txt
//image 폴더로 mv_test 파일을 옮겨준 후, 직접 이미지 폴더로 이동 후 list 확인을 통해 mv_test가 옮겨졌음을 확인
```

🔎cp와 관련된 자주 사용되는 명령어

```
cp <원본 파일명> <옮기고 싶은 디렉토리명>  //해당 디렉토리로 원본 파일 복사 
cp <원본 파일명> <복사해서 만들고 싶은 파일명> //해당 파일명으로 사본 파일 생성
cp <원본 파일명1> <원본 파일명2> <옮기고 싶은 디렉토리명>  //여러 파일을 한 번에 해당 렉토리로 복사
cp <원본 디렉토리> -r <옮기고 싶은 디렉토리명> //원본 디렉토리의 하위 파일까지 모두 해당 디렉토리로 복사
cp <원본 디렉토리> -r <복사해서 만들고 싶은 디렉토리명> //위의 방식을 응용해서 복사해서 만들고 싶은 디렉토리 생성
```

⌛cp 실습 코드 예시

```
# hcy12356@DESKTOP-A7B9I01:~/RedwoodK/image$ cp mv_test.txt practice
# cd practice
# hcy12356@DESKTOP-A7B9I01:~/RedwoodK/practice$
# ls
# mv_test.txt
```

🔎cat 명령어 사용법

```
cat <파일명1> <파일명2> ...  //기본적인 사용방법. 두 개 이상의 파일을 연달아 출력함
cat -n <파일명1> <파일명2> ...  //출력결과 앞에 행을 붙여서 출력
cat <파일명1> <파일명2> ... > <새로운 파일명>  //">" 앞에 있는 파일 내용을 합쳐 새로운 파일로 만들어줌
cat <파일명1> <파일명2> ... > <기존 파일명>  //">" 앞에 있는 파일 내용을 합쳐 기존 파일에 덮어씌움
cat <파일명1> <파일명2> ... >> <기존 파일명>  //">" 앞에 있는 파일 내용을 합쳐 기존 파일 뒤에 덧붙여줌
```

⌛cat 실습 코드 예시

```
//practice 폴더에 cat_test 파일을 임의로 생성한 후 진행
# cat mv_test.txt cat_test.txt
# mv testcat test.txt
```

🔎less 명령어 사용법

```
less <파일명>

[내부 창 단축키]
q: 종료 후 쉘창으로 복귀
enter: 1행 아래로 이동
space bar 또는 f: 아래로 1페이지 이동
숫자+n : 원하는 페이지만큼 뒤로 이동
PageUp: 위로 1페이지 이동
PageDown: 아래로 1페이지 이동
```

🔎tail 명령어 사용법

```
tail <파일명>  //기본형
tail text.txt  //1~35까지 입력된 텍스트 파일 중 마지막 10개 행이 출력됨
tail -n 5 <파일명>  //-n 뒤에 숫자를 입력하면, 마지막 행부터 해당 번째까지의 행이 출력됨
tail -c 10 <파일명>  //-c 뒤에 숫자를 입력하면, 행 기준이 아닌 byte 기준으로 출력됨
tail +25 <파일명>  //tail 뒤에 +숫자를 붙이면 해당 행부터 마지막 행까지 출력됨
tail -f <파일명>  //-f 를 붙이면, 종료되지 않은 채 실시간으로 마지막 10줄을 출력해줌. ctrl+c 로 종료
```

🔎rm과 관련된 자주 사용하는 명령어

```
rm <파일명>  //해당 파일을 삭제
rm *.txt  //.txt로 끝나는 모든 파일을 삭제
rm *  //전체 파일 삭제
rm -r <파일명/디렉토리명>  //해당 파일/디렉토리 삭제
rm -rf <파일명/디렉토리명>  //해당 파일/디렉토리 강제 삭제(경고문구 없이 삭제)
```

⌛rm 실습 코드 예시

```
# rm mv_test.txt
# hcy12356@DESKTOP-A7B9I01:~/RedwoodK/practice$ ls
# cat_test.txt mv_testcat_test.txt
//mv test 파일과 cat test, mv testcat test 파일 세 개가 있었지만 mv test.txt 파일이 사라져 나오지 않는다
```

🔎chown 명령어 사용법

```
chown <소유권자>:<그룹식별자> <소유권을 변경하고 싶은 파일명>  //해당 파일의 소유권자, 그룹식별자 변경
chown <소유권자>:<그룹식별자> <소유권을 변경하고 싶은 디렉토리명>  //해당 디렉토리의 소유권자, 그룹식별자 변경(하위 디렉토리는 변경 안됨)
chown -R <소유권자>:<그룹식별자> <소유권을 변경하고 싶은 파일명>  //해당 디렉토리 및 하위 디렉토리의 소유권자, 그룹식별자 변경
```

🔎grep 명령어 사옹법

```
grep <패턴> <파일명>...  //특정 파일에서 특정 패턴을 가진 문자열을 출력
grep <패턴> *  //현재 디렉토리 모든 파일에서 특정 패턴을 가진 문자열을 출력
grep <패턴> * -r  //현재 디렉토리 및 하위 디렉토리에서 특정 패턴을 가진 문자열을 출력
```

⌛grep 실습 코드 예시

```
// practice 폴더에 All I want for Christmas is you의 가사를 따온 txt 파일을 생성, 이후 명령어 실시
# grep 'Christmas' lyrics_grep_test.txt
# I don't want a lot for Christmas
# I don't care about the presents underneath the Christmas tree
# All I want for Christmas is you
# I don't want a lot for Christmas
# Don't care about the presents underneath the Christmas tree
# Santa Claus won't make me happy with a toy on Christmas Day
...

//Christmas가 포함된 줄의 전체 문자가 위처럼 나왔다, 라인이 많이 나와 후략
```

🔎ps 명령어 사용법

```
-a  //전체 사용자의 프로세스 출력
-u  //각 프로세스 사용자 및 사용시간 출력
-x  //제어 터미널이 없는 프로세스 출력
-l  //자세한 형태의 정보 출력
-e  //모든 프로세스 상태 출력

ps -aux  //BSD 구문을 사용하여 시스템의 모든 프로세스를 출력
ps -ejH  //프로세스를 트리형식으로 출력
```

⌛ps 실습 코드 예시

```
# hcy12356@DESKTOP-A7B9I01:~RedwoodK$ ps
#  PID TTY         TIME CMD
#   16 pts/0    00:00:00 sh
#   22 pts/0    00:00:00 sh
...
```

---

📘Shell Script - Basic Concepts; 기본 문법 및 작성 방법
---

❗📝#!/bin/bash
항상 최상단에는 #!/bin/bash가 적혀있어야 한다

```
# #!/bin/bash
# echo "hello world"
# hello

# printf "hello world"
# hello
```

▶️변수
변수명=값 으로 변수를 선언하고 사용할때는 앞에 $를 붙여준다; 중괄호를 이용하는 방법도 있는데, ${변수}, {변수}처럼 중괄호로 묶어서 사용

⌛실습 코드

```
# #!/bin/bash
# h = "hello"
# w = "world"
# echo "${h}, ${w}"
# 출력결과 : hello, world
```

▶️매개변수
프로그램에서 실행할 때 인자를 주는 것처럼 쉘 스크립트도 동일 방식 사용 가능

```
//실행한 스크립트 이름은 ${0}, 그 이후는 전달받은 인자 값이다

# #!/bin/bash
# echo "script name:${0}"
# echo "매개변수 갯수 :${#}"
# echo "전체 매개변수  값 : ${*}"
# echo "전체 매개변수 값2 : ${@}"
# echo "매개변수 1 : ${1}"
# echo "매개변수 2 : ${2}"
```

▶️예약변수
이미 정의된 변수로서, 사용자가 쉘 스크립트에서 따로 지정이 불가능한 변수들

변수 이름|설명
---|---
'HOME'|사용자 홈 디렉토리
'PATH'|실행 파일의 경로
'LANG'|프로그램 실행 시 지원되는 언어
'UID'|사용자의 UID
'SHELL'|사용자 로그인시 실행되는 쉘
'USER'|사용자의 계정 이름
'FUNCNAME'|현재 실행되고 있는 함수 이름
'TERM'|로그인 터미널


▶️배열
쉘 스크립트에서 배열은 1차원 배열만 지원하며 중괄호를 사용. 배열 원소를 소괄호 안 공백으로 구분하기 때문이며 배열 안 원소는 문자열 정수 상관 없이 사용 가능

```
//지정해둔 모든 변수를 삭제한 후 진행
# !/bin/bash

# arr=("Practice" "Shell" "Script" "Array" 1 2 3)

# echo "배열 전체 : ${arr[@]}"
# 배열 전체 : Practice Shell Script Array 1 2 3

# echo "배열 원소의 갯수: ${#arr[@]}"
# 배열 원소의 갯수: 7

# echo "배열 첫 번째 : ${arr},  혹은 ${arr[0]}"
# 배열 첫 번째 : Practice,  혹은 Practice

# echo "5번 index를 갖는 배월의 원소 : ${arr[5]}"
# 5번 index를 갖는 배월의 원소 : 1

# arr[5]="not five"
# echo "5번 index를 갖는 배월의 원소 : ${arr[5]}"
# 5번 index를 갖는 배월의 원소 : not five

# unset arr[5]
//5번의 원소를 해제

# echo "5번 index를 갖는 배열의 원소 : ${arr[5]}"
# 5번 index를 갖는 배열의 원소 :

# echo "6번 index를 갖는 배월의 원소 : ${arr[6]}"
# 6번 index를 갖는 배월의 원소 : 2
```

▶️함수
함수가 호출되기 전 미리 함수가 정의되어 있어야 하며, 괄호를 쓰지 않아야 한다

```
#!/bin/bash
 function test(){
     echo "mic check 1, 2, 3"
 }
 
# 함수 호출
# function test
# mic check 1, 2, 3

# 함수 호출
# test
# mic check 1, 2, 3
//함수를 호출할 때 function을 꼭 적지 않아도 위처럼 호출이 가능하다
```

▶️비교문
쉘 스크립트에서의 비교문은 형식이 정해져 있고, 이는 아래와 같다

```
if [ 값1 조건 값2 ]; then
	... 작업 내용 ...
fi
```

⌛실습 코드

```
function func(){
        a=10
        b=5

        if [ ${a} -eq ${b} ]; then
                echo "a와 b는 같다."
        fi

        if [ ${a} -ne ${b} ]; then
                echo "a와 b는 같지 않다"
        fi

        if [ ${a} -gt ${b} ]; then
                echo "a가 b보다 크다"
        fi

        if [ ${a} -ge ${b} ]; then
                echo "a가 b보다 크거나 같다"
        fi

        if [ ${a} -lt ${b} ]; then
                echo "a가 b보다 작다"
        fi

        if [ ${a} -le ${b} ]; then
                echo "a가 b보다 작거나 같다"
        fi

}

# 출력 결과
# a와 b는 같지 않다
# a가 b보다 크다
# a가 b보다 크거나 같다
```

▶️파일 관련 조건
조건|설명
---|---
`if [-d ${변수}]; then`|${변수}의 디렉토리가 존재하면 참이 성립합니다
`if[! -d ${변수}]; then`|${변수}의 디렉토리가 존재하지 않으면 참이 성립합니다
`if [ -e ${변수} ]; then `|${변수}라는 파일이 존재하면 참입니다
`if [ ! -e ${변수} ]; then |${변수}라는 파일이 존재하지 않으면 참입니다
`if [ -L ${변수} ]; then`|파일이 symbolic link이면 참입니다
`if [ -s ${변수} ]; then`|파일의 크기가 0보다 크면 참입니다
`if [ -S ${변수} ]; then`|파일 타입이 소켓이면 참입니다
`if [ -r ${변수} ]; then`|파일을 읽을 수 있으면 참입니다
`if [ -w ${변수} ]; then`|파일을 쓸 수 있으면 참입니다
`if [ -x ${변수} ]; then`|파일을 실행할 수 있으면 참입니다
`if [ -f ${변수} ]; then`|파일이 정규 파일이면 참입니다
`if [ -c ${변수} ]; then`|파일이 문자 장치이면 참입니다
`if [ ${변수1} -nt ${변수2}]; then`|변수1의 파일이 변수2의 파일보다 최신 파일이면 참입니다
`if [ ${변수1} -ot ${변수2}]; then`|변수1의 파일이 변수2의 파일보다 최신이 아니면 참입니다
`if [ ${변수1} -ef ${변수2}]; then`|변수1의 파일과 변수2의 파일이 동일하면 참입니다

🙋만약 AND 조건과 OR 조건을 섞어서 쓴다면?
+AND는 -a, OR은 -o를 이용해서 조건을 추가 할 수 있다
+또한, 여러 조건을 걸려면 C에서 switch case와 동일한 구문을 하는 문법도 존재한다

⌛실습 코드

```
# #!/bin/bash

# case ${1} in
        "linux") echo "리눅스" ;;
        "unix") echo "유닉스" ;;
        "windows") echo "윈도우즈" ;;
        "MacOS") echo "맥OS" ;;
        *) echo "머야" ;;
esac

# 출력 결과 : 머야
```

▶️반복문
+`break` 키워드의 사용을 통해 반복문을 멈출 수 있고, 위의 예제처럼 세미콜론을 두 개 (;;) 사용하는 것도 가능

⌛실습 코드

```
#!/bin/bash

# function tt2(){
        echo "Times Table 2"
        for i in {2..18..2}
        do
                echo "${i}"
        done
}

# tt2
//함수 호출

# Times Table 2
# 2
# 4
# 6
# 8
# 10
# 12
# 14
# 16
# 18
```

▶️명령어의 종료 코드
만약 명령어가 실패할 경우 동작을 다르게 할 것이라면 명령어의 종료 코드를 얻어오면 된다
+ 명령어의 종료 코드는 "$?" <- 가장 최근 실행한 명령어의 종료 코드가 있다
+ 정상적인 종료라면 0이 반환되는데, 0이 아닌 값으로 반환되면 오류이다

---

📗VIM 사용 방법
---

# VIM
유닉스에서 사용 가능한 에디터

# VIM 사용법

터미널에서 파일 생성하기

```
& vim hello.txt

// VIM 파일 만드는 방법
$ vim/vi 만들고자하는 파일 이름.파일의 확장자
```

+VIM에는 일반, 입력, 명령의 3가지 모드가 존재하며, 파일을 작성한 상태는 일반 상태이다

✋입력 모드
+a, i, s, o를 누르면 입력 모드로 들어올 수 있게 되며 파일을 작성하는 것이 가능해진다

```
# a
# -- INSERT --  
# 안녕하세요
# 저는 인턴이고 VIM을 베우고 있습니다
```

✋명령 모드
+ESC를 누르면 명령 모드로 들어가며, 위 입력 모드에서 나왔던 INSERT가 사라진다
```
: 을 누르면 눌러서 명령 콘솔을 활성화 해준다

:w = 저장
:q = 종료
:q! = 강제 종료

//저장을 하지 않고 종료를 하면 경고 창이 뜨면서 종료가 실행되지 않는데, 그때를 위한 강제 종료 명령어이다

:wq = 저장 & 종료
:wq! = 저장 & 강제 종료
```
