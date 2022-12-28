Day 2 - Linux 명령어
---
Linux command를 실습하고 각각의 기능에 대해 보고서를 제출하세요

+Basic Shell Commands
+Shell Script; Basic Concepts 기본 문법 및 작성 방법
+Vim 사용 방법

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

🔎cd

```
cd <Directory Name> // 가고자 하는 디렉토리로 이동
cd. //현재 디렉토리 확인
cd.. //상위 디렉토리로 이동
cd / //root, 최상위 디렉토리로 이동
cd $ 변수 이름 //변수 저장된 경로로 이동
cd ~ //사용자 디렉토리로 이동
cd $Home //사용자 디렉토리로 이동
cd //사용자 디렉토리로 이동
cd ~계정 이름 //입력한 사용자의 home 디렉토리로 이동
cd- // 이전 경로로 이동
```

⌛cd 실습 코드 예시

```
**hcy12356@DESKTOP-A7B9I01:~$**
**_cd RedwoodK_**
**_cd ._**
//RedwoodK 디렉토리로 이동 및 결과 확인

**hcy12356@DESKTOP-A7B9I01:~/RedwoodK$**
**_cd practice_**
**_cd ._**
//RedwoodK의 하위 디렉토리인 practice로 이동 및 결과 확인

**hcy12356@DESKTOP-A7B9I01:~/RedwoodK/practice$**
**_cd .._**
**_cd ._**
//상위 디렉토리인 RedwoodK로 이동 및 결과 확인

**hcy12356@DESKTOP-A7B9I01:~/RedwoodK$**
```

🔎ls

```

```

```
** day1-github구성.md  day2-linux명령어.md**
