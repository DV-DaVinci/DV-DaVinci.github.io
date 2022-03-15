---
title: STS4에서 DataBase 연결
date: 2022-03-10 00:26:00 +09:00 
categories: [WindowOS, STS4] 
tags: [setting]     # TAG names should always be lowercase
---

STS4에서 DataBase 연결하는 방법입니다.

---

- 환경
    
    Spring Tool Suite 4
    
    Oracle DataBase21C
    
    ojdbc 11
    
    Window11 / 64bit 운영체제
    

---

## Window > Show View 에서 Data Source Explorer를 Open

![0.png](/assets/2022-03-10-Connect-DataBase/0.png)

## Database Connections 우클릭 > New

![1.png](/assets/2022-03-10-Connect-DataBase/1.png)

## Oracle 선택 후 Next

![2.png](/assets/2022-03-10-Connect-DataBase/2.png)

## 오른쪽 상단 New Driver Definition ⊕아이콘 클릭

![3.png](/assets/2022-03-10-Connect-DataBase/3.png)

## Name/Type 탭에서 Oracle Thin Driver | Oracle | 11 을 선택

![4.png](/assets/2022-03-10-Connect-DataBase/4.png)

## JAR List 탭에서 원래 추가되어 있던 ojdbc 파일을 remove

![5.png](/assets/2022-03-10-Connect-DataBase/5.png)

## Add JAR > ojdbc 설치 경로로 들어가서 ojdbc11 선택

![6.png](/assets/2022-03-10-Connect-DataBase/6.png)

![7.png](/assets/2022-03-10-Connect-DataBase/7.png)

## Properties탭 확인 후 OK 클릭

![8.png](/assets/2022-03-10-Connect-DataBase/8.png)

## SID : orcl / Host : localhost / User name: 계정 아이디 / Password: 계정 비밀번호 입력 후 Test Connection 클릭

![9.png](/assets/2022-03-10-Connect-DataBase/9.png)

## Ping succeeded!가 뜨면 Connect 성공

![10.png](/assets/2022-03-10-Connect-DataBase/10.png)

## Next > Finish 후 다음과 같이 'New Oracle'이 추가되어있으면 성공

![12.png](/assets/2022-03-10-Connect-DataBase/11.png)
![13.png](/assets/2022-03-10-Connect-DataBase/12.png)