Day 1 - Github 구성
RedWoodK 인턴 과제
---
github에 계정을 따고, 과제제출용 repository를 생성하세요

wsl을 이용한 linux 환경구성 방법에 대해 보고서를 제출하시요

Github Account & Repository
---

📧Github_Account_Email ; <hcy_@naver.com>

📂Github_Repository ; [RedWoodK](https://github.com/ChangYeonHwang/RWK_Intern_Report)


WSL을 이용한 Linux 환경 구성 방법
---
WSL = Windows Subsystem for Linux
리눅스를 위한 윈도우의 서브시스템으로서, 윈도우에서 리눅스를 구현할 수 있게 도와주는 툴


💿WSL 설치 방법

1. Microsoft 10 2004 Update 확인

2. Windows Powershell을 관리자 권한으로 실행한 후, 다음 명령어를 입력하여 WSL을 활성화한다

```
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```
 
3. 다음 명령어를 입력하여 WSL의 VM Platform 옵션 기능을 사용할 수 있도록 설정한다

```
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
``` 
![img for wsl2 installation](https://user-images.githubusercontent.com/87057782/209558072-3b906e79-37bd-4d30-9eac-e19d8a63387d.png)

4.  윈도우를 재부팅한다

5. Microsoft Store에서 Ubuntu를 검색, 설치해준다

6. 아래의 그림 같은 화면이 나오면 Username과 Password를 설정해준다

![Ubuntu installation](https://user-images.githubusercontent.com/87057782/209558093-ee34cf70-2fe9-4a9e-87ca-69814518f32f.png)


7. Windows Powershell을 관리자 권한으로 실행한 후, 다음 명령어를 입력하여 WSL2로 업그레이드 해준다

```
wsl --set-default-version 2
wsl --set-version Ubuntu 2
```

8. 업그레이드가 잘 되었는지 확인을 위한 아래의 명령어를 입력하여 현재 버젼을 확인해 볼 수 있다

```
wsl -l -v
```

 📎참고 링크 ; <https://dos-soles.tistory.com/24>

2022.12.22
