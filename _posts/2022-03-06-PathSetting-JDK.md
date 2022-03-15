---
title: PathSetting JDK
date: 2022-03-06 10:26:00 +09:00 
categories: [WindowOS, JDK]
tags: [setting]     # TAG names should always be lowercase
---

Window에서 JDK 설치 후, `환경변수 설정`하는 방법입니다.

---

- 환경

    JAVA_VERSION="17.0.2"<br>
    JAVA_VERSION_DATE="2022-01-18"<br>
    LIBC="default"<br>
    OS_ARCH="x86_64"<br>
    OS_NAME="Windows"<br>

---

1. `Window key + r key` 를 누르고, 실행창에서 `sysdm.cpl`을 검색합니다.
    
    ![0.png](/assets/2022-03-06-PathSetting-JDK/0.png)
    
2. `고급` 탭에서 `환경 변수`를 클릭합니다.
    
    ![1.png](/assets/2022-03-06-PathSetting-JDK/1.png)
    
3. 하단의 `시스템 변수` 에서 `새로 만들기`를 클릭합니다.
    
    ![2.png](/assets/2022-03-06-PathSetting-JDK/2.png)
    
4. 변수 이름을 `JAVA_HOME` 으로 하고, 변수 값은 `본인 JDK 설치 경로`로 설정합니다. 
    
    ![4.png](/assets/2022-03-06-PathSetting-JDK/3.png)
    
5. 그 다음 `Path` 으로 들어갑니다.
    
    ![6.png](/assets/2022-03-06-PathSetting-JDK/4.png)
    
6. `새로 만들기`를 클릭합니다.
    
    ![7.png](/assets/2022-03-06-PathSetting-JDK/5.png)
    
7. `%JAVA_HOME%\bin` 을 적어줍니다.
    
    ![8.png](/assets/2022-03-06-PathSetting-JDK/6.png)
    
8. `위로 이동`을 눌러서 맨 위로 올려줍니다.
    
    ![10.png](/assets/2022-03-06-PathSetting-JDK/7.png)
    
9. 그 다음 `확인`을 눌러줍니다.
    
    ![11.png](/assets/2022-03-06-PathSetting-JDK/8.png)
    
10. cmd창에서 다음과 같이 차례로 입력해줍니다. 
    
    ![‘path’를 입력했을 때 경로를 살펴보면 맨 앞으로 온 jdk 경로를 확인할 수 있습니다. ](/assets/2022-03-06-PathSetting-JDK/9.png)
    
    `path`를 입력했을 때 경로를 살펴보면 `맨 앞으로 온 jdk 경로`를 확인할 수 있습니다.