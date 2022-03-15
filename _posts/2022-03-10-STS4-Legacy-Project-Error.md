---
title: Spring Legacy Project 생성 오류
date: 2022-03-10 11:31:00 +09:00 
categories: [WindowOS, STS4] 
tags: [setting]     # TAG names should always be lowercase
---

STS4에서 `Spring Legacy Project`를 생성할 때 

```
an error has occurred. see error log for more details. java.lang.exceptionininitializererror
```

이런 오류 문구가 뜬다면 이 포스팅을 참고하시기 바랍니다.

---

- 환경
    
    Spring Tool Suite 4
    
    Window11 / 64bit 운영체제
    

---

`New > Other`로 들어가 `Spring Legacy Project`를 생성합니다.

![0.png](/assets/2022-03-10-STS4-Legacy-Project-Error/0.png)

![1.png](/assets/2022-03-10-STS4-Legacy-Project-Error/1.png)

Project name을 쓰고 Templates은 `Spring MVC Project`를 선택 후 생성하려고 하면 다음과 같은 팝업창이 뜹니다. 라이브러리를 받겠다는 뜻이므로 `Yes`를 누릅니다.

![2.png](/assets/2022-03-10-STS4-Legacy-Project-Error/2.png)

다음의 오류창이 떴습니다.

![3.png](/assets/2022-03-10-STS4-Legacy-Project-Error/3.png)

![4.png](/assets/2022-03-10-STS4-Legacy-Project-Error/4.png)

검색을 해보니 Spring Legacy Project는 아직 JDK17을 지원하지 않는데, Spring 자체에서는 JDK17을 지원해서 이런 문제가 발생한 것 같습니다.
[spring 공식 홈페이지](https://spring.io/blog/2021/09/15/spring-tools-4-12-0-released)에도 'Java 17 지원 가능'을 확인할 수 있습니다.

![스크린샷(102).png](/assets/2022-03-10-STS4-Legacy-Project-Error/4-1.png)

기존 JDK17을 지우고 JDK11을 재설치 했습니다. (JDK를 재설치 시 환경변수 설정도 다시 해주어야 합니다.)

![5.png](/assets/2022-03-10-STS4-Legacy-Project-Error/5.png)

그 다음 STS4 설치 경로에서 `SpringToolSuite4.ini` 파일을 들어갑니다.
![스크린샷(100).png](/assets/2022-03-10-STS4-Legacy-Project-Error/5-1.png)

\- vm
plugins/org.eclipse.justj.openjdk.hotspot.jre.full.win32.x86_64_17.0.1.v20211116-1657/jre/bin

밑에<br>
\- vm
C:\DevProgram\Java\bin\javaw.exe

이렇게 적어줍니다.

![스크린샷(101).png](/assets/2022-03-10-STS4-Legacy-Project-Error/6.png)

다시 STS4에서 `Spring Legacy Project`를 생성해봅니다.

![7.png](/assets/2022-03-10-STS4-Legacy-Project-Error/7.png)

문제 없이 다음 단계로 넘어갑니다.

```
Please specify the top-level package e.g. com.mycompany.myapp*
```

이 단계에서 `com.mycompany.myapp`과 같은 형식으로 적어줍니다.

![8.png](/assets/2022-03-10-STS4-Legacy-Project-Error/8.png)

`Spring Legacy Project`가 만들어졌습니다.

![9.png](/assets/2022-03-10-STS4-Legacy-Project-Error/9.png)