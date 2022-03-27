---
title: GitHub Pages B
date: 2022-03-27 06:10:00 +09:00 
categories: [Git, Pages] 
tags: [Git, Pages]     # TAG names should always be lowercase
---

---

- 환경
    
    git version 2.35.1.windows.2
    
    ruby 3.1.1p18 (2022-02-18 revision 53f5fc4236) [x64-mingw-ucrt]
    
    Window11 / 64bit 운영체제
    

---

## Tools/init.sh

GitHub Pages A에서 `Jekyll serve`를 통해 로컬 서버에서 구동한 Page는 Chirpy의 소개 페이지 입니다.

커스텀을 하기 위해서는 기본 컨텐츠를 지워야 합니다. 

Git Bash를 켜서 cd 명령어로 Pages 디렉토리로 이동 후, 아래 명령어를 적어줍니다. (MacOS는 Terminal을 사용합니다.)

```
$ bash tools/init.sh
```

다시 로컬 서버를 가동시키면 기본 컨텐츠가 사라집니다. 

## _Config.yml

```yml
# The Site Configuration

# Import the theme
theme: jekyll-theme-chirpy # import하는 테마 명, 수정 X 

# 사용자 페이지를 만들었을 경우, 빈칸으로 둡니다. 프로젝트 페이지를 만들었을 경우에만 프로젝트 명을 적어줍니다.
# 저는 사용자 페이지를 만들었기 때문에 빈칸으로 두겠습니다. 
baseurl: ''

# 사용하는 언어 설정을 진행합니다. http://www.lingoes.net/en/translator/langcode.htm 로 접속하여 확인이 가능합니다.
lang: en

# 날짜/시간 현지화를 위한 추가 매개변수, 선택사항. › https://github.com/iamkun/dayjs/tree/dev/src/locale
# 이것도 빈칸으로 둡니다.
prefer_datetime_locale:

# timezone을 설정합니다. › http://www.timezoneconverter.com/cgi-bin/findzone/findzone
timezone: Asia/Seoul

# jekyll-seo-tag settings › https://github.com/jekyll/jekyll-seo-tag/blob/master/docs/usage.md
# ↓ --------------------------

title: Davinci Note            # 블로그 이름입니다.

tagline:  DV-DaVinci's Blog.   # 서브 타이틀입니다.

description: >-                # 블로그 설명입니다.
  Do Develop. Like Davinci.

#'https://username.github.io'와 같이 설정합니다.
url: 'https://dv-davinci.github.io'

github:
  username: DV-Davinci         # 본인의 GitHub username을 적습니다.

twitter:
  username: DavinciWdv         # 본인의 twitter username을 적습니다.

social:
  # Change to your full name.
  # It will be displayed as the default author of the posts and the copyright owner in the Footer
  name: DV-DaVinci
  email: wdvdavinci@gmail.com            # change to your email address
  links:
    # The first element serves as the copyright owner's link
    - https://twitter.com/DavinciWdv    # change to your twitter homepage
    - https://github.com/DV-DaVinci       # change to your github homepage
    # Uncomment below to add more social links
    # - https://www.facebook.com/username
    # - https://www.linkedin.com/in/username

# 상단은 social 관련 내용입니다. 본인의 이름, 이메일, 링크 등을 작성합니다. 저는 깃허브와 트위터만 올렸습니다.

google_site_verification:    # Google Search Console 관련 내용입니다. 

# ↑ --------------------------
# The end of `jekyll-seo-tag` settings

google_analytics:
  id:                # Google Analytics ID입니다.
  # Google Analytics pageviews report settings
  pv:
    proxy_endpoint:   # fill in the Google Analytics superProxy endpoint of Google App Engine
    cache_path:       # the local PV cache data, friendly to visitors from GFW region

theme_mode: dark ## chirpy테마는 [light|dark]테마를 지원합니다. 저는 dark로 했습니다. 

img_cdn: #cdn 이미지 설정입니다. 저는 빈칸으로 두었습니다. 

# 대표 이미지입니다. 
avatar: /assets/img/Avatar/Avatar.jpg

# toc(Table of contents)입니다. 블로그를 보다보면 포스팅 우측에 스크롤을 따라오는 목차입니다.
# 사용하려면 true, 아니라면 false를 적으면 됩니다.
toc: true

#--------------이후 내용은 건들지 않았으므로 생략합니다.---------------
```

## ⚠️Error

- Gemfile.lock

‘Chirpy’ 테마는 현재 시점에서 Push를 하면 _Config.xml이 제대로 적용되지 않습니다. 

여러번 같은 과정을 반복하며 분석해본 결과 tools/init.sh 명령이 .gitignore에 있는 Gemfile.lock을 삭제시킨다는 사실을 발견했습니다. 

이후 Gemfile.lock 파일을 아예 삭제한 후 Push를 하니 정상적으로 반영되었습니다. 

- Local Server

Gemfile.lock을 삭제하면 local server 에서 구동이 불가합니다. 때문에 삭제보다는 .gitignore에 Gemfile.lock 추가를 권장합니다.

작성자는 수정사항이 있다면 VS Code로 고치고 GitHub Desktop으로 Push 하는 형식으로 포스팅을 올리고 있어서 loacl server 구동 없이도 별다른 어려움 없이 포스팅을 하고 있습니다.

## Push

![스크린샷(165).png](/assets/2022-03-27-GitHub-Pages-B/1.png)

Push 한 후, GitHub 의 Actions 탭을 확인하면 페이지 반영 결과를 확인할 수 있습니다.