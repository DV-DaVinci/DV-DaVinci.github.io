---
title: Git Setting
date: 2022-03-19 05:53:00 +09:00 
categories: [Git, git] 
tags: [setting]     # TAG names should always be lowercase
---

- git 설치 후 setting 방법입니다.

---

- 환경
    
    git version 2.35.1.windows.2
    
    Window11 / 64bit 운영체제
    

---

## Git Bash 실행

![스크린샷(151).png](/assets/2022-03-19-Git-Setting/1.png)

## 사용자 이름 / 이메일 등록

```
git config --global user.name "사용자이름"
git config --global user.email "이메일@abc.com"
```

## 등록된 사용자 확인

```
git config --list
```

![스크린샷(153).png](/assets/2022-03-19-Git-Setting/2.png)