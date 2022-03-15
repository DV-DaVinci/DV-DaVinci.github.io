---
title: Other Environment Setting
date: 2022-03-07 09:45:00 +09:00 
categories: [WindowOS, STS4]
tags: [setting]     # TAG names should always be lowercase
---

Spring Legacy Project를 생성하고 준비가 끝났다고 생각했지만, 기존에 사용했던 `Data Source Explorer` 탭이나 `HTML, CSS, SQL File`도 없는 것을 확인했습니다.

STS4에서 `Data Source Explorer` 및 `HTML, CSS, SQL File` 생성 방법입니다.

---

- 환경
    
    Spring Tool Suite 4<br>
    
    Version: 4.13.1.RELEASE<br>
    
    Window11 / 64bit 운영체제<br>
    

---

1. `Help > Install New Software`로 들어갑니다.
    
    ![12.png](/assets/2022-03-07-STS4-Other-Environment-Setting/0.png)
    
2. `Latest Eclipse Release - https://download.eclipse.org/releases/photon`을 적어줍니다.
    
    ![13.png](/assets/2022-03-07-STS4-Other-Environment-Setting/1.png)
    
3. `Database Development`와 `Web, XML, Java EE and OSGi Enterprise Development`를 체크하고 `Next` 합니다.
    
    ![14.png](/assets/2022-03-07-STS4-Other-Environment-Setting/2.png)
    
    ![15.png](/assets/2022-03-07-STS4-Other-Environment-Setting/3.png)
    
    ![16.png](/assets/2022-03-07-STS4-Other-Environment-Setting/4.png)
    
4. `Install Details` 창이 뜨면 그대로 `Next` 합니다.
    
    ![17.png](/assets/2022-03-07-STS4-Other-Environment-Setting/5.png)
    
5. `라이센스 동의` 후, `Finish` 합니다.
    
    ![18.png](/assets/2022-03-07-STS4-Other-Environment-Setting/6.png)
    
6. 다운 중, `Trust` 창이 뜨면 `Select All`을 누르고 `Trust selected` 합니다.
    
    ![20.png](/assets/2022-03-07-STS4-Other-Environment-Setting/7.png)
    
7. Restart 창이 뜨면 `Restart Now`를 클릭합니다.
    
    ![21.png](/assets/2022-03-07-STS4-Other-Environment-Setting/8.png)
    
8. 다시 `Window > Show View` 에서 `‘data’`를 검색하면 `Data Source Explorer`가 생겼습니다. 나중에 쓸 예정이므로 `Open` 해줍니다.
    
    ![22.png](/assets/2022-03-07-STS4-Other-Environment-Setting/9.png)
    
    ![23.png](/assets/2022-03-07-STS4-Other-Environment-Setting/10.png)
    
9. `Servers`도 나중에 `Tomcat`이 설치되면 사용할 예정이므로 미리 `Open` 해줍니다.
    
    ![24.png](/assets/2022-03-07-STS4-Other-Environment-Setting/11.png)
    
    ![25.png](/assets/2022-03-07-STS4-Other-Environment-Setting/12.png)
    
10. `Window > Preferences` 에서 `HTML Files`, `CSS Files`, `JSP Files`, `XML Files`, `Workspace`를 `UTF-8`로 설정해줍니다.
    
    ![28.png](/assets/2022-03-07-STS4-Other-Environment-Setting/13.png)
    
    ![29.png](/assets/2022-03-07-STS4-Other-Environment-Setting/14.png)
    
    ![30.png](/assets/2022-03-07-STS4-Other-Environment-Setting/15.png)
    
    ![31.png](/assets/2022-03-07-STS4-Other-Environment-Setting/16.png)
    
    ![33.png](/assets/2022-03-07-STS4-Other-Environment-Setting/17.png)
    
    여기까지 왔다면, STS4에서 Spring Legacy Project를 할 준비가 다 된겁니다.