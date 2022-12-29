Day 3 - Git 명령어
---
Git 명령어를 실습하고 각각의 기능에 대해 보고서를 제출하세요

❓What is Git?
---

Git은 분산 버전 관리 시스템으로, 다수의 이용자가 접근 가능하며 여러 작업을 진행 가능하다는 장점을 갖고 있다

+ Branch, Merge 기능을 통한 여러 작업의 진행 및 충돌 관리의 용이
+ Server와 통신할 필요가 없으며 로컬에서 작업이 이루어져 빠르다
+ 로컬 원격 저장소에 데이터가 복제되기 때문에 안정성이 좋다
+ 데이터의 무결성이 보장되는 방식으로, 커밋 ID를 통해 이를 확인할 수 있다

Git 기본 명령어
---

🔎Git init
---
로컬 Git 저장소를 설정합니다.

⌛실습 코드

```
# mkdir sample
# cd sample
# touch red orange
# echo "빨강" >> red
# echo "주황" >> orange
# git init
# Initialized empty Git repository in /home/ChangYeonHwang/RWK_Intern_Report/git/sample/.git/
```

```
mkdir  //디렉토리 생성
cd  //디렉토리 이동
touch  //빈 파일 생성
echo "[문자]" >> [파일]  //파일에 글자 추가
```

Git status, git add
---

🔎Git Add
파일의 변경사항을 인덱스에 추가, Git은 커밋하기 전 인덱스에 먼저 파일을 추가

🔎Git Status
현재 작업중인 상태를 확인합니다

---

⌛실습 코드

```
# git config --global user.name 'ChangYeonHwang'
# git config --global user.email 'hcy_@naver.com"
//git 접속하기

git remote add origin https://github.com/ChangYeonHwang/RWK_Intern_Report.git
//repo 연결하기

# git status
# On branch master
# No commits yet
# Untracked files:
#  (use "git add <file>..." to include in what will be committed)
#        hello.txt
#        sample/
#
# nothing added to commit but untracked files present (use "git add" #to track)

# git add .
# git status
# On branch master
#
# No commits yet
#
# Changes to be committed:
#  (use "git rm --cached <file>..." to unstage)
#        new file:   orange
#        new file:   red
```

🔎Git Commit
현재 상태 저장, 인덱스에 추가된 변경 사항을 이력에 추가합니다

---

⌛실습 코드

```
git commit -m "20221229:Git명령어연습"
#[master (root-commit) 625q45d] 20221229:Git명령어연습
# 2 files changed, 2 insertions(+)
# create mode 100644 orange
# create mode 100644 red
```

⌛다양한 변화 주기 실습 코드

```
💻작업 과정

1. red 삭제
2. orange에 내용 추가
3. green 파일 추가
4. 상태 확인
5. 전체 파일 인덱스에 추가
6. 세 번째 이력 커밋

# rm red
# echo "오렌지" >> orange
# touch green
# git status
# On branch master
# Changes not staged for commit:
#  (use "git add/rm <file>..." to update what will be committed)
#  (use "git restore <file>..." to discard changes in working #directory)
#        deleted:    red

# Untracked files:
#  (use "git add <file>..." to include in what will be committed)
#        green
#        orange
# no changes added to commit (use "git add" and/or "git commit -a")

# git add -A
# git commit -m "20221229:GitVariousChanges"
# 3 files changed, 1 insertion(+), 1 deletion(-)
# create mode 100644 orange
# create mode 100644 green
# delete mode 100644 red
```

🔎Git Log
이력 확인 가능, 다양한 옵션을 조합하여 원하는 형태의 로그를 출력할 수 있는 강력한 기능 


⌛실습 코드

```
# git log
# commit 365as615s3265sta3526n185o63v26j1655l2j32 (HEAD -> master)
# Author: ChangYeonHwang <hcy_@naver.com>
# Date:   Thu Jul 29 17:15:26 2022 +0900
#
#     20221229:GitVariousChanges


# commit a85909ba91f8b56ea26b3a2764d1dd9b749cee86
# Author: ChangYeonHwang <hcy_@naver.com>
# commit a85909ba91f8b56ea26b3a2764d1dd9b749cee86
# Author: ChangYeonHwang <hcy_@naver.com>
# Date:   Thu Jul 29 17:24:05 2022 +0900
#
#     20221229:Git명령어연습
```

🔎Git reset
이전 상태로 이력 제거, 특정 커밋의 이력을 초기화 시키며 n번 전까지의 작업 내용 취소

⌛실습 코드

```
# git reset 625q45d --hard
# HEAD is now at 625q45d 20221229:Git명령어연습
```

🔎Git Revert
이전 상태로 이력 유지

```
작업 과정
1. git reset 명령어로 인해 GitVariousChanges가 사라졌기 때문에 다시 작업을 해준다
2. hit log로 커밋 ID를 다시 조회해서 확인
3. git revert로 커밋을 취소

# rm red
# echo "오렌지" >> orange
# touch green
# git status
# On branch master
# Changes not staged for commit:
#  (use "git add/rm <file>..." to update what will be committed)
#  (use "git restore <file>..." to discard changes in working #directory)
#        deleted:    red

# Untracked files:
#  (use "git add <file>..." to include in what will be committed)
#        green
#        orange
# no changes added to commit (use "git add" and/or "git commit -a")

# git add -A
# git commit -m "20221229:GitVariousChanges"
# [master s1w122j] 20221229:GitVariousChanges
# 3 files changed, 1 insertion(+), 1 deletion(-)
# create mode 100644 green
# create mode 100644 orange
# delete mode 100644 red
```
