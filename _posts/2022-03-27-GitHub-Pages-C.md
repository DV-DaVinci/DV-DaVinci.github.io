---
title: GitHub Pages C
date: 2022-03-27 09:03:00 +09:00 
categories: [Git, Pages] 
tags: [Git, Pages]     # TAG names should always be lowercase
---

---

- 환경
    
    git version 2.35.1.windows.2
    
    ruby 3.1.1p18 (2022-02-18 revision 53f5fc4236) [x64-mingw-ucrt]
    
    Window11 / 64bit 운영체제
    

---

## Favicon

Favicon은 웹 브라우저의 주소창에 표시되는 웹사이트나 웹페이지를 대표하는 아이콘입니다.  작성자가 사용중인 ‘Chirpy’ 테마는 디폴트 Favicon이 수박을 먹고 있는 개미로 설정되어 있습니다. 

작성자는 블로그 컨셉에 맞게 Favicon을 교체했습니다. 

### Generate Favicon

‘Chirpy’ wiki의 Favicon([https://chirpy.cotes.page/posts/customize-the-favicon/](https://chirpy.cotes.page/posts/customize-the-favicon/)
)에서 추천하고 있는 ‘Real favicon generator([https://realfavicongenerator.net](https://realfavicongenerator.net/)
)’를 사용해 간단히 생성할 수 있습니다. 

![스크린샷(167).png](/assets/2022-03-27-GitHub-Pages-C/1.png)

‘Select your Favicon image’를 클릭하여 Favicon image를 첨부합니다. 

![스크린샷(169).png](/assets/2022-03-27-GitHub-Pages-C/2.png)

Favicon Generator Options에서 화면과 같이 체크하고, Pages의 favicon 디렉토리 경로를 입력합니다. 입력 후, 아래 Generate your Favicons and HTML code 버튼을 클릭합니다. 

![스크린샷(170).png](/assets/2022-03-27-GitHub-Pages-C/3.png)

Favicon package를 다운로드하고 기존의 Favicon 디렉토리에 대치한 후 Push 합니다. 

### Safari 대응 HTML 삽입

- ‘Chirpy’ 테마의 경우 Safari에 대응하는 HTML이 없어, Safari에서는 Favicon 적용이 안 될 수 있습니다. 때문에 _includes/favicon.html에 Safari 관련 코드를 삽입해야 합니다.

![스크린샷(193).png](/assets/2022-03-27-GitHub-Pages-C/4.png)

Inatall your favicon에서 safari 관련 코드를 복사합니다.

![스크린샷(194).png](/assets/2022-03-27-GitHub-Pages-C/5.png)

`_includes/favicon.html`에 Safari 관련 코드를 삽입합니다.

![스크린샷(195).png](/assets/2022-03-27-GitHub-Pages-C/6.png)

Push하기 전, safari 해당 파일이 Pages favicon 디렉토리에 있는지 확인합니다.

## Comment Box

Jekyll 기반의 블로그의 대부분은 Disqus를 사용하는 것 같습니다.

그러나 Disqus는 무겁고, 무료 라이센스로 사용하는 경우 광고가 붙어 미관상 좋지 않습니다. 

그래서 다른 대안을 찾던 중 utterances 라는 대체제를 찾을 수 있었습니다. 

### utterances

utterances는 상대적으로 가볍고, GitHub Repository의 Issue를 이용하기 때문에, 메일로 댓글 알림을 받을 수 있다는 장점이 있습니다. 

### Create Repository

작성자는 깔끔하게 관리하고 싶어서 댓글용 Repository를 추가로 생성했습니다. 

![스크린샷(171).png](/assets/2022-03-27-GitHub-Pages-C/7.png)

### Install utterance

[https://github.com/apps/utterances](https://github.com/apps/utterances)로 접속합니다.

![스크린샷(131).png](/assets/2022-03-27-GitHub-Pages-C/8.png)

Install 버튼을 누릅니다.

![스크린샷(132).png](/assets/2022-03-27-GitHub-Pages-C/9.png)

Install 후 작성자는 지정된 공간에서 관리하고자 따로 Comments Repo를 생성했기 때문에,  ‘Only select repositories’를 선택했습니다. 

![스크린샷(175).png](/assets/2022-03-27-GitHub-Pages-C/10.png)

[https://utteranc.es/](https://utteranc.es/) 로 접속 후, Configuration의 Repository의 repo: 에

`GitHub Name/Repo Name`을 입력합니다. 

![스크린샷(176).png](/assets/2022-03-27-GitHub-Pages-C/11.png)

댓글 이슈를 댓글 달린 블로그 페이지의 어떤 부분과 매핑시킬지 key를 결정합니다.

매핑시키는 것이기 때문에 key가 달라지면 Value는 사라질겁니다. 

때문에 수정을 할 일이 거의 없는 pathname을 선택하는 것이 좋겠습니다. 

![스크린샷(177).png](/assets/2022-03-27-GitHub-Pages-C/12.png)

Theme 에서 utterances의 테마를 설정합니다. 저는 GitHub Dark를 선택했습니다. 이후 Enable Utterances 코드를 Copy 합니다. 

### Set

![스크린샷(178).png](/assets/2022-03-27-GitHub-Pages-C/13.png)

`_layouts/post.html` 맨 하단에 복사+붙이기 한 후 Push 합니다. 

![스크린샷(179).png](/assets/2022-03-27-GitHub-Pages-C/14.png)

## Search Engine Optimization

SEO는 검색엔진 최적화, 즉 검색엔진에서 찾기 쉽도록 사이트를 개선하는 프로세스입니다. 

작성자는 해외 개발자들과도 소통하는 것을 목표로 하고 있어 해외 접근성이 좋은 Google에서 진행하겠습니다. 

### Google Search Console

![스크린샷(180).png](/assets/2022-03-27-GitHub-Pages-C/15.png)

Google Search Console([https://search.google.com/search-console/about](https://search.google.com/search-console/about)
) 로 접속합니다. 

![스크린샷(139).png](/assets/2022-03-27-GitHub-Pages-C/16.png)

‘시작하기’를 클릭하면 URL 접두어를 선택한 뒤, 자신의 Pages의 주소를 입력합니다.

![스크린샷(186).png](/assets/2022-03-27-GitHub-Pages-C/17.png)

다음의 HTML파일을 다운로드 합니다.

![스크린샷(140).png](/assets/2022-03-27-GitHub-Pages-C/18.png)

다운로드한 html 파일을 Pages 디렉토리에 배치한 후 Push 합니다.

![스크린샷(141).png](/assets/2022-03-27-GitHub-Pages-C/19.png)

Push가 완료되면 소유권 확인이 가능합니다. 

### Sitemap.xml

sitemap.xml은 크롤러가 웹 사이트 색인을 잘할 수 있도록 하는 일종의 지도입니다. 

저는 직접 작성하기 보다 자동생성 사이트를 이용하겠습니다. 

[https://www.xml-sitemaps.com](https://www.xml-sitemaps.com/)로 접속합니다.

![스크린샷(142).png](/assets/2022-03-27-GitHub-Pages-C/20.png)

검색창에 Pages 주소를 입력하고 Start 합니다.

![스크린샷(143).png](/assets/2022-03-27-GitHub-Pages-C/21.png)

진행이 완료되면, View Sitemap Details 를 클립합니다. 

![스크린샷(144).png](/assets/2022-03-27-GitHub-Pages-C/22.png)

Download your XML Sitemap file을 클릭합니다. 

![스크린샷(145).png](/assets/2022-03-27-GitHub-Pages-C/23.png)

이후 다운로드 받은 XML 파일을 Pages 디렉토리로 이동해줍니다. 

### robots.txt

Pages 디렉토리에 robots.txt 파일을 생성한 후, 아래 양식대로 작성합니다.

```
User-agent: Googlebot
Disallow: /nogooglebot/

User-agent: *
Allow: /

Sitemap: http://www.example.com/sitemap.xml
```

![스크린샷(196).png](/assets/2022-03-27-GitHub-Pages-C/24.png)

### Check

![스크린샷(190).png](/assets/2022-03-27-GitHub-Pages-C/25.png)

<Pages주소>/sitemap.xml 로 접속하여 확인해봅니다. 


### Add Sitemap

![스크린샷(148).png](/assets/2022-03-27-GitHub-Pages-C/26.png)

![스크린샷(197).png](/assets/2022-03-27-GitHub-Pages-C/27.png)

Google Search Console 사이드바의 Sitemap을 클릭하고 sitemap.xml을 입력하고 제출합니다. 

![스크린샷(198).png](/assets/2022-03-27-GitHub-Pages-C/28.png)

이후 크롤링 완료까지 ‘가져올 수 없음’ 상태가 표시됩니다. 

오류는 아니니 걱정하지 않아도 됩니다. 

길게는 약 하루정도 소요됩니다.