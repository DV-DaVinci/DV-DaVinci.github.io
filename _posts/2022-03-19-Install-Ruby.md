---
title: Install Ruby
date: 2022-03-19 07:26:00 +09:00 
categories: [WindowOS, Ruby] 
tags: [setting]     # TAG names should always be lowercase
---

Window에서 `Ruby` 설치 방법입니다. 

- Jekyll이 `Ruby`로 만들어져 있어서 Jekyll설치 전, 먼저 설치하도록 하겠습니다.

---

- 환경
    
    ruby 3.1.1p18 (2022-02-18 revision 53f5fc4236) [x64-mingw-ucrt]
    
    Window11 / 64bit 운영체제
    

---

### Ruby Download

[https://rubyinstaller.org/downloads/](https://rubyinstaller.org/downloads/) 로 들어가서 `Ruby+Devkit 3.1.1-1 (x64)`를 다운합니다.

![스크린샷(154).png](/assets/2022-03-19-Install-Ruby/1.png)

### 설치 파일 실행 후 라이센스 동의

라이센스 동의 후 `Next` 합니다.

![스크린샷(60).png](/assets/2022-03-19-Install-Ruby/2.png)

### Installation Destination and Optional Tasks

원하는 경로를 지정하고 `Next` 합니다.

![스크린샷(62).png](/assets/2022-03-19-Install-Ruby/3.png)

### Select Components

그대로 `Next` 합니다.

![스크린샷(63).png](/assets/2022-03-19-Install-Ruby/4.png)

### Installing

![스크린샷(64).png](/assets/2022-03-19-Install-Ruby/5.png)

### 설치 완료

`Finish`를 클릭합니다. 

![스크린샷(65).png](/assets/2022-03-19-Install-Ruby/6.png)

### RubyInstaller2

잠시 후, CMD창이 실행되면서 다음과 같은 화면이 나옵니다.

![스크린샷(66).png](/assets/2022-03-19-Install-Ruby/7.png)

1,2,3 을 차례로 설치를 해줍니다.

### 설치된 Ruby Version 확인하기

cmd 창을 열어 `ruby -v` 를 입력합니다. 

```
ruby -v
```

다음과 같은 결과를 얻을 수 있습니다.

```
ruby 3.1.1p18 (2022-02-18 revision 53f5fc4236) [x64-mingw-ucrt]
```