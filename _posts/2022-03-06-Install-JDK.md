---
title: Install JDK
date: 2022-03-06 09:49:00 +09:00 
categories: [WindowOS, JDK]
tags: [setting]     # TAG names should always be lowercase
---

Window에서 `JDK17`을 설치하는 방법입니다. 

- 저는 현재 JDK11을 사용하고 있으나, 설치 방법은 동일하니 참고해주시기 바랍니다.

---

- 환경

    JAVA_VERSION="17.0.2"<br>
    JAVA_VERSION_DATE="2022-01-18"<br>
    LIBC="default"<br>
    OS_ARCH="x86_64"<br>
    OS_NAME="Windows"<br>

---

1. Google에서 `JDK17`을 검색합니다.
    
    ![1.png](/assets/2022-03-06-Install-JDK/1.png)
    
2. 제일 위에 있는 사이트에 들어갑니다.
    
    ![2.png](/assets/2022-03-06-Install-JDK/2.png)
    
3. `이 사이트의 쿠키에 대하여`라는 팝업창이 뜨면 ‘모두 승인’을 클릭합니다.
    
    ![3.png](/assets/2022-03-06-Install-JDK/3.png)
    
4. 그 다음 화면에서 스크롤을 조금 내려줍니다.
    
    ![4.png](/assets/2022-03-06-Install-JDK/4.png)
    
5. `Windows x64 Installer`를 다운해줍니다. (각자의 환경에 맞게 다운합니다.)
    
    ![5.png](/assets/2022-03-06-Install-JDK/5.png)
    
6. 설치를 진행합니다.
    
    ![6.png](/assets/2022-03-06-Install-JDK/6.png)
    
    ![7.png](/assets/2022-03-06-Install-JDK/7.png)
    
    ![8.png](/assets/2022-03-06-Install-JDK/8.png)
    
    ![9.png](/assets/2022-03-06-Install-JDK/9.png)
    
    ![10.png](/assets/2022-03-06-Install-JDK/10.png)
    
    ![11.png](/assets/2022-03-06-Install-JDK/11.png)
    
7. 설치가 완료되면, cmd 창을 열어 `javac -version`을 입력했을 때 버전명이 잘 나오면 잘 설치된 겁니다. 
    
    ![cmd1.png](/assets/2022-03-06-Install-JDK/cmd1.png)
    

