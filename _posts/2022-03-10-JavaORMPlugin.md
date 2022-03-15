---
title: Java ORM Plugin 수동 설치
date: 2022-03-10 01:49:00 +09:00 
categories: [WindowOS, STS4] 
tags: [setting]     # TAG names should always be lowercase
---


## Java ORM Plugin을 설치하려고 하는데 아래와 같은 어려움을 겪고 계신가요?

- Eclipse MarketPlace에 ‘java orm plugin’ 을 검색하면 나오지 않습니다.
- [https://marketplace.eclipse.org/search/site/orm](https://marketplace.eclipse.org/search/site/orm) 으로 접속해서 ‘orm’을 검색합니다.
- 맨 위에 보라색 마크가 Java ORM Plugin인데, Eclipse에 드래그해서 install 하라고 되어 있지만 드래그해보면 아무일도 일어나지 않습니다.

저 역시 구글링을 통해 여러 블로그들을 돌아다니며 이것저것 시도해보았으나 여러 번 실패를 했고, 결국 저만의 수동설치 노하우가 생겨 블로그에 기록해봅니다. 

(아무래도 Java ORM Plugin이 더 이상 서비스를 안 하는 것 같습니다. 방법은 수동설치뿐입니다.)

STS4에서 `Java ORM Plugin` 수동설치 방법입니다.

---

- 환경
    
    Spring Tool Suite 4
    
    JavaORMPlugin_1.0.0.201411180016
    
    Window11 / 64bit 운영체제
    

---

1. [https://sourceforge.net/](https://sourceforge.net/) 에 들어가 ‘java orm plugin’을 검색합니다.
    
    ![5.png](/assets/2022-03-10-JavaORMPlugin/1.png)
    
    ![6.png](/assets/2022-03-10-JavaORMPlugin/2.png)
    
2. 다운로드 합니다. (약 5초정도 걸립니다.)
    
    ![8.png](/assets/2022-03-10-JavaORMPlugin/3.png)
    
3. C 드라이브에 다운받은 zip파일을 풀어줍니다.
    
    ![10.png](/assets/2022-03-10-JavaORMPlugin/4.png)
    
4. 풀어준 후 `JavaORMPlugin` 폴더에 들어갑니다.
    
    ![11.png](/assets/2022-03-10-JavaORMPlugin/5.png)
    
    ![12.png](/assets/2022-03-10-JavaORMPlugin/6.png)
    
5. features 폴더로 들어가 안에 있는 파일 이름을 복사합니다.(f2 누르고 Ctrl+C)
    
    ![13.png](/assets/2022-03-10-JavaORMPlugin/7.png)
    
6. 다시 전으로 돌아와서 features 폴더명을 방금 복사한 파일명으로 바꿔줍니다.
    
    ![14.png](/assets/2022-03-10-JavaORMPlugin/8.png)
    
7. 그 다음, STS4 설치 경로로 들어가면 그곳에도 features라는 폴더가 있습니다. (저 같은경우 C드라이브 > STS4 > sts-4.13.1.RELEASE> features 로 들어갑니다.)
    
    ![15.png](/assets/2022-03-10-JavaORMPlugin/9.png)
    
8. ORM 폴더에서 방금 이름을 바꿔준 features를 STS4에 있는 features로 옮겨줍니다.
    
    ![16.png](/assets/2022-03-10-JavaORMPlugin/10.png)
    
9. `ORM 폴더`에 `plugins`로 들어가면 `JavaORMPlugin_1.0.0.201411180016.jar` 파일이 있습니다.
    
    ![17.png](/assets/2022-03-10-JavaORMPlugin/11.png)
    
10. 그리고 다시 전으로 돌아오면 `artifacts`, `content` 라는 jar파일도 있습니다.
    
    ![18.png](/assets/2022-03-10-JavaORMPlugin/12.png)
    
11. 9번,10번에 언급한 모든 jar파일을 STS4 설치 경로에 있는 plugins 폴더에 옮겨줍니다.(저 같은경우 C드라이브 > STS4 > sts-4.13.1.RELEASE > plugins 로 들어갑니다.)
12. STS4 설치 경로에 `configuration` 폴더로 들어갑니다.
    
    ![19.png](/assets/2022-03-10-JavaORMPlugin/13.png)
    
13. `org.eclipse.equinox.simpleconfigurator` 라는 파일을 찾아서 들어갑니다.
    
    ![20.png](/assets/2022-03-10-JavaORMPlugin/14.png)
    
14. 그곳에 `bundles.info` 라는 파일을 `VS Code`로 열어줍니다. 
    
    ![21.png](/assets/2022-03-10-JavaORMPlugin/15.png)
    
15. `VS code`가 없다면 설치합니다.
    
    ![22.png](/assets/2022-03-10-JavaORMPlugin/16.png)
    
    ![23.png](/assets/2022-03-10-JavaORMPlugin/17.png)
    
    ![24.png](/assets/2022-03-10-JavaORMPlugin/18.png)
    
    ![25.png](/assets/2022-03-10-JavaORMPlugin/19.png)
    
    ![26.png](/assets/2022-03-10-JavaORMPlugin/20.png)
    
    ![27.png](/assets/2022-03-10-JavaORMPlugin/21.png)
    
    ![28.png](/assets/2022-03-10-JavaORMPlugin/22.png)
    
    ![29.png](/assets/2022-03-10-JavaORMPlugin/23.png)
    
    ![30.png](/assets/2022-03-10-JavaORMPlugin/24.png)
    
    ![31.png](/assets/2022-03-10-JavaORMPlugin/25.png)
    
    ![32.png](/assets/2022-03-10-JavaORMPlugin/26.png)
    
16. `#encoding=UTF-8`

    `#version=1`

    밑에  
    `1.0.0.201411180016,plugins/me.karthy.plugin.java.orm.feature_1.0.0.201411180016.jar,4,false`

    이렇게 적어주고 저장합니다.

    ![33.png](/assets/2022-03-10-JavaORMPlugin/27.png)

1. STS4 를 실행하고 `Window > Show View` 에서 `plug-ins`를 `Open`합니다.
    
    ![34.png](/assets/2022-03-10-JavaORMPlugin/28.png)
    
2. 하단에 `JavaORMPlugin`이 추가 되어있으면 성공입니다. (저렇게 뜨면 무조건 성공입니다.)
    
    ![35.png](/assets/2022-03-10-JavaORMPlugin/29.png)
    
3. 10분~20분 뒤에 `Ctrl+N` 눌러서 `Java ORM Plugin`이 추가됐는지 확인합니다. 
    (반영되는게 느리기 때문에 조금 기다렸다가 확인하는게 좋습니다.)
    ![36.png](/assets/2022-03-10-JavaORMPlugin/30.png)
