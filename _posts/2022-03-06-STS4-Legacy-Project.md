---
title: Spring Legacy Project 생성
date: 2022-03-07 01:27:00 +09:00 
categories: [WindowOS, STS4]
tags: [setting]     # TAG names should always be lowercase
---

STS4를 설치하면 `Spring Legacy Project`가 없습니다. 

기존 Eclipse 버전(Eclipse Photon version)에서 `Spring Legacy Project`를 계속 사용해왔던지라 많이 당황했습니다. 

STS4에서 `Spring Legacy Project`를 생성하는 방법은 다음과 같습니다.

---

- 환경
    
    Spring Tool Suite 4<br>
    
    Version: 4.13.1.RELEASE<br>
    
    Window11 / 64bit 운영체제<br>
    

---

1. STS4 설치 후, `Ctrl+N` 을 누르고 `‘spring’`을 검색해보면 `Spring Legacy Project`가 없습니다.
    
    ![0.png](/assets/2022-03-06-STS4-Legacy-Project/0.png)
    
2. `Help > Eclipse Marketplace` 로 들어갑니다.
    
    ![1.png](/assets/2022-03-06-STS4-Legacy-Project/1.png)
    
3. `‘sts’` 를 검색하고, `Spring Tools 3 Add-On for Spring Tools 4 3.9.21.RELEASE` 를 `Install`합니다.
    
    ![2.png](/assets/2022-03-06-STS4-Legacy-Project/2.png)
    
4. 전부 체크되어 있는지 확인 후, `Confirm` 합니다.
    
    ![3.png](/assets/2022-03-06-STS4-Legacy-Project/3.png)
    
5. `라이센스 동의` 후, `Finish` 합니다.
    
    ![4.png](/assets/2022-03-06-STS4-Legacy-Project/4.png)
    
6. 우측 하단 구석에 다운되고 있는 모습을 확인할 수 있습니다. (기다리면 Restart 팝업창이 뜹니다.)
    
    ![5.png](/assets/2022-03-06-STS4-Legacy-Project/5.png)
    
7. `Restart` 후, 전에 없던 `Dashboard`가 생겼습니다.
    
    ![6.png](/assets/2022-03-06-STS4-Legacy-Project/6.png)
    
8. 다시 `Ctrl+N` 을 눌러서 `‘spring’`을 검색해보면 `Spring Legacy Project`가 생겼습니다.
    
    ![7.png](/assets/2022-03-06-STS4-Legacy-Project/7.png)