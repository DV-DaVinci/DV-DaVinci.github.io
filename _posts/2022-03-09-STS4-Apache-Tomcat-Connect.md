---
title: STS4에서 Apache Tomcat 연동
date: 2022-03-09 07:34:00 +09:00 
categories: [WindowOS, STS4]
tags: [setting]     # TAG names should always be lowercase
---

STS4에서 `Apache Tomcat 연동`하는 방법입니다.

- 저는 현재 `JDK11`로 바꾼 상태이지만 과정은 똑같으니 참고부탁드립니다.

---

- 환경

    Spring Tool Suite 4
    
    Apache Tomcat Version 10.0.16
    
    JAVA_VERSION="17.0.2"
    
    Window11 / 64bit 운영체제
    

---

1. `Window > Show View`에서 `Servers`를 `Open`합니다.
2. `No servers are available. click this link to create a new server...` 문구를 클릭합니다.
3. `New Server`창에서 `Apache`를 선택하고 `Tomcat v10.0 Server`를 선택 후 `Next`합니다.
    
    ![10.png](/assets/2022-03-09-STS4-Apache-Tomcat-Connect/0.png)
    
4. `Browse`를 클릭하고 `Apache Tomcat 설치 경로로` 들어가 `apache-tomcat-10.0.16`를 선택합니다.
    
    ![11.png](/assets/2022-03-09-STS4-Apache-Tomcat-Connect/1.png)
    
    ![12.png](/assets/2022-03-09-STS4-Apache-Tomcat-Connect/2.png)
    
    ![13.png](/assets/2022-03-09-STS4-Apache-Tomcat-Connect/3.png)
    
5. `Installed JREs`에서 `Add`를 누른 후 `Standard VM`를 선택 후 `Next` 합니다.
    
    ![14.png](/assets/2022-03-09-STS4-Apache-Tomcat-Connect/4.png)
    
    ![15.png](/assets/2022-03-09-STS4-Apache-Tomcat-Connect/5.png)
    
    ![16.png](/assets/2022-03-09-STS4-Apache-Tomcat-Connect/6.png)
    
6. `Directory`에서 `JDK 설치 경로로(bin 직전까지)` 들어가 폴더 선택 후 `Finish` 합니다.
    
    ![17.png](/assets/2022-03-09-STS4-Apache-Tomcat-Connect/7.png)
    
    ![18.png](/assets/2022-03-09-STS4-Apache-Tomcat-Connect/8.png)
    
    ![19.png](/assets/2022-03-09-STS4-Apache-Tomcat-Connect/9.png)
    
7. `방금 추가한 JDK`를 `체크`하고 `Apply and Close` 합니다. 
    
    ![20.png](/assets/2022-03-09-STS4-Apache-Tomcat-Connect/10.png)
    
8. `JRE:` 에서 `방금 추가한 JDK`를 `선택` 후 `Finish` 합니다.
    
    ![21.png](/assets/2022-03-09-STS4-Apache-Tomcat-Connect/11.png)
    
    ![22.png](/assets/2022-03-09-STS4-Apache-Tomcat-Connect/12.png)
    
9. 이런 화면이 되면 성공입니다.
    
    ![23.png](/assets/2022-03-09-STS4-Apache-Tomcat-Connect/13.png)