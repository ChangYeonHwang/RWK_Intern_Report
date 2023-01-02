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
![img for wsl2 installation](https://user-images.githubusercontent.com/87057782/209783923-64e17c3e-880e-4c7f-a33a-687a37967c7d.png)

4.  윈도우를 재부팅한다

5. Microsoft Store에서 Ubuntu를 검색, 설치해준다

6. 아래의 그림 같은 화면이 나오면 Username과 Password를 설정해준다

![Ubuntu installation](https://user-images.githubusercontent.com/87057782/209558093-ee34cf70-2fe9-4a9e-87ca-69814518f32f.png)


7. Windows Powershell을 관리자 권한으로 실행한 후, 다음 명령어를 입력하여 WSL2로 업그레이드 해준다

```
wsl --set-default-version 2
wsl --set-version Ubuntu 2

//wsl 설치 중 문제가 생긴다면, Linux 커널 패키지가 업데이트가 안 되어있어 그럴 확률이 높다
  밑의 링크를 통해 Linux 커널 업데이트 패키지를 진행한다
  
[패키지 업데이트](https://learn.microsoft.com/ko-kr/windows/wsl/install-manual#step-4---download-the-linux-kernel-update-package)
```

8. 업그레이드가 잘 되었는지 확인을 위한 아래의 명령어를 입력하여 현재 버젼을 확인해 볼 수 있다

```
wsl -l -v
```

💿코드 에디터 설치 및 터미널 설정
---
리눅스를 다룰 코드 에디터를 설치하고, 관련 설정을 해준다

코드 에디터에는 VS Code, Visual Studio, Notepad ++ 등 여럿 있지만 그 중에서도 많은 사람들이 쓰는 VS Code를 예시로 들었다


1. [VS Code 설치](https://code.visualstudio.com/)

2. VS Code 확장에서 Remote - WSL을 검색하여 다운로드 해준다

3. VS Code 터미널 설정

VSCode의 내장 터미널을 Windows에서 Ubuntu(WSL)로 바꾸어서 설정하여 준다
![Terminal Ubuntu](https://user-images.githubusercontent.com/87057782/209782732-ff09b69a-f280-4004-af66-ad91264e57bf.png)



 📎참고 링크 ; <https://dos-soles.tistory.com/24>, <https://velog.io/@njw1204/%EC%9C%88%EB%8F%84%EC%9A%B0%EC%97%90-%EB%A6%AC%EB%88%85%EC%8A%A4-%EA%B0%9C%EB%B0%9C-%ED%99%98%EA%B2%BD-%EA%B5%AC%EC%B6%95%ED%95%98%EA%B8%B0>

2022.12.22
