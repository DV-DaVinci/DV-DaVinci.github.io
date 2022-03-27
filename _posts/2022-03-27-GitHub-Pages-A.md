---
title: GitHub Pages A
date: 2022-03-27 04:15:00 +09:00 
categories: [Git, Pages] 
tags: [Git, Pages]     # TAG names should always be lowercase
---

---

- 환경
    
    git version 2.35.1.windows.2
    
    ruby 3.1.1p18 (2022-02-18 revision 53f5fc4236) [x64-mingw-ucrt]
    
    Window11 / 64bit 운영체제
    

---

## GitHub 블로그를 시작한 이유

개발자에게 포트폴리오는 굉장히 중요한 요소입니다. 작성자는 지나온 족적과 앞으로의 활동을 기록하는 공간으로 네이버 블로그를 이용했었습니다. 그런데 얼마 전부터 구글링을 할 때마다 주소창에 ‘github.io’ 라는 문구를 접하게 됐습니다.

‘github’는 기존에 STS4로 프로젝트를 진행하면서 기록용으로 많이 이용을 해왔었지만, github로 블로그를 만들 수 있다는 사실은 이로써 처음 알게 되었습니다. 

## Naver 블로그에서 GitHub 블로그로

github.io란 무엇인지 구글링을 통해 조사한 결과 블로그 이사를 결심했습니다.

GitHub와 연동되어 커밋기록을 남길 수 있다는 점과 커스터마이징 기능이 상당히 매력적이었고, 향후 캐나다 취업을 목표로 하고 있기 때문에 네이버 블로그보다 해외 유입 접근성이 용이하다는 측면에서도 좋다고 느꼈습니다.

## Install Ruby

Jekyll 테마를 이용하여 github pages를 만들것이기 때문에 Ruby와 Jekyll을 다운해야 합니다.

Jekyll이 Ruby로 만들어졌기 때문에 Jekyll 설치 전, Ruby를 먼저 설치합니다.

WindowOS : [https://dv-davinci.github.io/posts/Install-Ruby/](https://dv-davinci.github.io/posts/Install-Ruby/)

MacOS : [https://dv-davinci.github.io/posts/Ruby-on-MacOS/](https://dv-davinci.github.io/posts/Ruby-on-MacOS/)

## Install Jekyll

MacOS는 Terminal, WindowOS는 Ruby 프롬포트를 사용합니다.

![1.png](/assets/2022-03-27-GitHub-Pages-A/1.png)

아래 명령을 입력합니다.

```
gem install Jekyll bundler
```

## Jekyll 설치 확인

![2.png](/assets/2022-03-27-GitHub-Pages-A/2.png)

`Jekyll -v`를 입력해 설치를 확인합니다.

## Jekyll Theme

지킬 테마는 [http://jekyllthemes.org](http://jekyllthemes.org/) 에서 원하는 테마를 선택할 수 있습니다.

![스크린샷(156).png](/assets/2022-03-27-GitHub-Pages-A/3.png)

작성자는 목차가 직관적이고 가독성이 좋은  https://github.com/cotes2020/jekyll-theme-chirpy 를 선택했습니다.

테마 선택 후 압축파일을 다운하는 방법도 있지만 GitHub를 사용하겠습니다.

## Fork

![스크린샷(157).png](/assets/2022-03-27-GitHub-Pages-A/4.png)

  https://github.com/cotes2020/jekyll-theme-chirpy 로 이동해서 좌측상단의 Fork를 클릭합니다.

![스크린샷(158).png](/assets/2022-03-27-GitHub-Pages-A/5.png)

Fork된 모습입니다.

### Repository name 수정

![스크린샷(159).png](/assets/2022-03-27-GitHub-Pages-A/6.png)

Repo의 이름을 아래의 형식으로 수정합니다.

```
<GitHubName>.github.io

Ex: DV-DaVinci.github.io
```

## Clone

GitHub의 Repository를 Clone합니다. 저는 GitHub Desktop을 사용합니다.

GitHub Desktop 다운 : [https://desktop.github.com/](https://desktop.github.com/) 

![스크린샷(160).png](/assets/2022-03-27-GitHub-Pages-A/7.png)

저는 path를 원하는 대로 수정한 후 Clone 했습니다.

![스크린샷(162).png](/assets/2022-03-27-GitHub-Pages-A/8.png)

GitHub Pages가 Clone 된 모습입니다.

![스크린샷(163).png](/assets/2022-03-27-GitHub-Pages-A/9.png)

조금 전 path에 파일이 생성되었습니다. 

## Connect Local Server

![스크린샷(164).png](/assets/2022-03-27-GitHub-Pages-A/10.png)

Ruby 프롬포트를 킵니다.

![스크린샷(79).png](/assets/2022-03-27-GitHub-Pages-A/11.png)

cd 명령어를 통해 page 저장소로 이동 후 `bundle install`을 입력해 의존성 모듈을 설치합니다. 

![스크린샷(82).png](/assets/2022-03-27-GitHub-Pages-A/12.png)

설치가 완료되면 `jekyll serve`를 입력해 local server를 구동합니다.

![스크린샷(83).png](/assets/2022-03-27-GitHub-Pages-A/13.png)

Server adress로 접속해보면 테마가 적용된 Page를 확인할 수 있습니다. 

Command+C 혹은 Ctrl + C를 누르면 Server를 종료할 수 있습니다.