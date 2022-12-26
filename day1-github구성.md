Day 1 - Github 구성
RedWoodK 인턴 과제
---

Github Account & Repository

📧Github_Account_Email ; <hcy_@naver.com>
📂Github_Repository ; <>
---

WSL을 이용한 Linux 환경 구성 방법

WSL = Windows Subsystem for Linux
리눅스를 위한 윈도우의 서브시스템으로서, 윈도우에서 리눅스를 구현할 수 있게 도와주는 툴로 현재 WSL2가 릴리스 되어 사용된다


💿WSL 설치 방법

1. Microsoft 10 2004 Update 확인

  WSL2는 마이크로소프트에서 정식으로 릴리스한 툴이기 때문에 윈도우의 특정 버젼 이상부터 지원이 된다
    
2. Windows Powershell을 관리자 권한으로 실행한 후, 다음 명령어를 입력하여 WSL을 활성화한다

```
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```
 
3. 다음 명령어를 입력하여 WSL의 VM Platform 옵션 기능을 사용할 수 있도록 설정한다

```
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
``` 

4.  윈도우를 재부팅한다

5. Microsoft Store에서 Ubuntu를 검색, 설치해준다
    Ubuntu는 리눅스의 배포판 소프트웨어 중 하나로, 무료일 뿐 아니라 편의성도 뛰어나 가장 많은 유저들이 사용하는 소프트웨어이다
    다운로드가 완료됐다면 아이디와 패스워드를 설정해준다
 
    이와 같은 작업을 마쳤으면, 다운 받은 WSL을 Version 2로 변경해주기 위한 작업이 필요하다
 
6. Windows Powershell을 관리자 권한으로 실행한 후, 다음 명령어를 입력하여 WSL2로 업그레이드 해준다

```
wsl --set-default-version 2
wsl --set-version Ubuntu 2
```

   업그레이드가 잘 되었는지 확인을 위한 아래의 명령어를 입력하여 현재 버젼을 확인해 볼 수 있다

```
wsl -l -v
```

 📎참고 링크 ; <https://dos-soles.tistory.com/24>

2022.12.22
