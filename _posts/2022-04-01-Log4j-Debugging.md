---
title: Log4j Error Debugging
date: 2022-04-01 09:53:00 +09:00 
categories: [Debugging] 
tags: [Spring, Log4j]     # TAG names should always be lowercase
---

---

- 환경
    
    Spring Tool Suite 4
    Version: 4.13.1.RELEASE
    
    OS_ARCH="x86_64"
    OS_NAME="Windows"
    

---

## Spring MVC 생성 후 log4j.xml 에러 발생

Spring MVC 프로젝트를 생성하였는데, log4j.xml에서 빨간줄 에러가 발생했다.

![스크린샷(211).png](/assets/2022-04-01-Log4j-Debugging/1.png)

## 해결방법

해결방법은 DOCTYPE 태그를 아래와 같이 대체했다.

```java
<!DOCTYPE log4j:configuration SYSTEM "http://logging.apache.org/log4j/1.2/apidocs/org/apache/log4j/xml/doc-files/log4j.dtd">
```

![스크린샷(213).png](/assets/2022-04-01-Log4j-Debugging/2.png)