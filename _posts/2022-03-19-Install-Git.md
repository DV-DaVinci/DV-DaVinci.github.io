---
title: Install Git
date: 2022-03-19 04:54:00 +09:00 
categories: [Git, git] 
tags: [setting]     # TAG names should always be lowercase
---

Window에서 Git을 설치하는 방법입니다.

- git을 사용하려면 git 회원가입이 필요합니다. 회원가입은 [https://github.com/](https://github.com/) 에서 간단히 가능합니다.
- git 설치 시 `Visual Studio Code`를 기본 에디터로 선택할 것입니다. (VS code가 없는 분들은 미리 설치 하시기 바랍니다.)

---

- 환경
    
    git version 2.35.1.windows.2
    
    Window11 / 64bit 운영체제
    

---

## Download

[https://git-scm.com/](https://git-scm.com/) 으로 들어가서 Downloads에서 본인의 환경에 맞는 것을 다운합니다.

(저는 Standalone Installer > `64-bit Git for Windows Setup`을 다운했습니다.)

![스크린샷(3).png](/assets/2022-03-19-Install-Git/1.png)

## Install

다운 후 설치를 진행합니다.

### Git Setup 프롬포트 진행

![스크린샷(4).png](/assets/2022-03-19-Install-Git/2.png)

`Next`를 눌러 진행합니다.

### Select Destination Location

![스크린샷(5).png](/assets/2022-03-19-Install-Git/3)

저는 Depth가 깊은 것을 안 좋아해서 C 드라이브에 지정된 폴더로 설정했습니다.

### Select Components

![스크린샷(6).png](/assets/2022-03-19-Install-Git/4.png)

기본 상태 그대로 진행해도 무방합니다만, 원한다면 같이 설치되는 구성 요소를 선택합니다.

- 옵션
    - Additional icons, On the Desktop : 바탕화면에 바로가기 아이콘 추가
    - Windows Explorer intergration
        - Git Bash Here : Git Bash 연결 기능
        - Git GUI Here : Git GUI 연결 기능
    - Git LFS(Large File Support): 용량이 큰 파일 지원 여부
    - Associate .git Configuration files with the default text editor : Git 구성 파일을 기본 텍스트 편집기와 연결할지 여부
    - Associate .sh files to be run with Bash : .sh 확장자 파일을 Bash와 연결할지 선택
    - Check daily for Git for Windows updates : Git 업데이트를 매일 체크할지 여부
    - Add a Git Bash Profile to Windows Terminal: 윈도우 터미널에 Git Bash를 추가

### Select Start Menu Folder

![스크린샷(7).png](/assets/2022-03-19-Install-Git/5.png)

시작 폴더 경로를 지정 후 `Next`를 눌러 진행합니다.

(Don’t create a Start Menu folder 선택 박스를 체크하면 추가 되지 않습니다.)

### Choosing the default editor used by Git

![스크린샷(25).png](/assets/2022-03-19-Install-Git/6.png)

Git의 기본 에디터를 선택 후 `Next`를 눌러 진행합니다.

저는 VSCode를 자주 사용하므로 VSCode를 선택 후 Next 했습니다.

### Adjusting the name of the initial branch in new repositories

![스크린샷(27).png](/assets/2022-03-19-Install-Git/7.png)

새 Repository를 생성할 때 initial branch 이름을 지정하는 방법을 선택 후 `Next` 합니다. (Let Git decide를 선택 후 Next)

✅Let Git decide : 새로운 Repository의 initial branch에 기본 분기 이름(”master”)를 사용합니다. 

Override the default branch name for new repositories : 새로운 Repository의 initial branch에 사용자 지정 분기 이름을 사용합니다. 이미 팀에서 관용적으로 쓰는 명칭이 있을 때 사용하면 됩니다.

### Adjusting your PATH environment

![스크린샷(28).png](/assets/2022-03-19-Install-Git/8.png)

Git 커맨드를 사용하기 위한 환경변수를 설정하고 `Next` 합니다.

Use Git from Git Bash only : Git Bash에서만 Git 명령어를 수행할 수 있습니다.

✅ Git from the command line and also from 3rd-party software : Git 환경변수(PATH)에 추가하여 윈도우 기본 명령 프롬포트(CMD) 등 에서도 Git 명령어를 수행할 수 있습니다.

Use Git and optional Unix tools from the Command Prompt : Git과 Unix 도구 모두 환경변수(PATH)에 추가합니다. 

### Choosing the SSH executable

![스크린샷(29).png](/assets/2022-03-19-Install-Git/9.png)

SSH 실행 도구를 선택하고 `Next` 합니다.

✅ Use bundled OpenSHH : Git에서 기본으로 제공되는 OpenSSH를 사용합니다.

Use external OpenSSH : 외부 OpenSHH를 사용합니다. 이 경우 Git에서 기본 제공하는 OpenSSH는 따로 설치되지 않으며 PATH에 명시된 OpenSSH를 사용합니다.

### Choosing HTTPS transport backend

![스크린샷(30).png](/assets/2022-03-19-Install-Git/10.png)

HTTP 연결 옵션을 선택하고 `Next` 합니다.

✅ Use the OpenSSL library : OpenSSL 라이브러리를 사용합니다. ca-bundle.crt 파일을 검증합니다.

Use the native Windows Secure Channel library : Windows 인증서 저장소를 사용하여 검증합니다. 이 옵션은 Activce Directory 도메인 서비스를 통한 회사의 내부 Root CA 인증서를 사용할 수 있습니다. 

### Configuring the line ending conversions

![스크린샷(31).png](/assets/2022-03-19-Install-Git/11.png)

Git 저장소에 체크인/아웃할 때의 줄 바꿈 방법을 선택하고 `Next` 합니다.

- 윈도우와 유닉스의 개행 표기가 서로 다릅니다.(윈도우: \r\n 유닉스:\n)
    
    따라서 여러 운영체제에서 작업할 경우, 개행 표기가 달라져 수정 사항이 없음에도 수정된 것으로 인식할 가능성이 있습니다. 이를 해결하기 위한 옵션입니다. 
    
    ✅ Checkout Windows-style, commit Unix-style line endings : 체크아웃은 윈도우 스타일, 커밋은 유닉스 스타일로 자동 변경되도록 설정합니다. 
    
    Checkout as-is, commit Unix-style line endings : 체크아웃은 변경 없이, 커밋은 유닉스 스타일로 설정합니다.
    
    Checkout as-is, commit as-is : 체크아웃, 커밋 모두 스타일 변경 없이 진행합니다.
    

### Configuring the terminal emulator to use with Git Bash

![스크린샷(32).png](/assets/2022-03-19-Install-Git/12.png)

Git Bash 터미널 에뮬레이터를 선택하고 `Next` 합니다.

✅ Use MinTTY (the default terminal of MSYS2) : Git Bash 기본 터미널 에뮬레이터(MinTTY)를 사용합니다.

Use Windows’ default console window : 윈도우 기본 콘솔(cmd)을 사용합니다.

### Choose the default behavior of ‘git pull’

![스크린샷(33).png](/assets/2022-03-19-Install-Git/13.png)

‘git pull’ 명령어에 수행될 작업을 선택하고 `Next` 합니다. 

✅ Default (fase-forward or merge) : ‘git pull’의 수행 동작을 기본으로 설정합니다.

Rebase : ‘git pull’의 수행 동작으로 현재 분기를 불러온 분기를 재배치합니다.

Only ever fase-forward : ‘git pull’의 수행 동작으로 불러온 분기로 빠르게 넘어갑니다. 명령어 수행에 실패할 가능성이 있습니다. 

### Choose a credential helper

![스크린샷(34).png](/assets/2022-03-19-Install-Git/14.png)

자격 증명 도우미를 선택하고 `Next`를 눌러줍니다. 

✅Git Credential Manager Core : Git의 자격 증명 도우미를 사용합니다.

None : 자격 증명 도우미를 사용하지 않습니다. 

### Configuring extra options

![스크린샷(35).png](/assets/2022-03-19-Install-Git/15.png)

기타 옵션을 선택하고 `Next` 눌러줍니다.

✅ Enable file system cashing : 파일 시스템 캐싱을 활성화하며 상당한 성능 향상을 제공합니다. 

Enable symbolic links : 심볼릭 링크를 활성화합니다. (seVreateSymbolicLink 권한이 필요합니다.) 기존 레포지토리에는 이 설정이 적용되지 않습니다. 

### Configuring experimental options

![스크린샷(36).png](/assets/2022-03-19-Install-Git/16.png)

실험적 기능 사용 여부를 선택하고 `Install`을 눌러줍니다.

(말 그대로 실험적 기능, 개발중인 기능들입니다. Git에 익숙하지 않다면 선택하지 않는 것을 권장합니다.)

Enable experimental support for pseudo consoles :  winpty를 사용하지 않고 Git Bash에서 Node나 Python과 같은 콘솔을 실행할 수 있게 합니다. 그러나 몇 가지 버그가 있습니다. 

Enable experimental built-in file system monitor : ‘git status’ , ‘git commit’ 등과 같은 명령어 실행 속도를 높이기 위해 built-in file system monitor를 자동으로 실행합니다. 

### Completing the Git Setup Wizard

![스크린샷(37).png](/assets/2022-03-19-Install-Git/17.png)

`Finish`를 눌러 설치를 완료합니다.