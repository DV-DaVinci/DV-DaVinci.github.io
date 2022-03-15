---
title: Oracle DataBase 21C 계정 생성
date: 2022-03-09 11:09:00 +09:00 
categories: [WindowOS, Oracle]
tags: [setting]     # TAG names should always be lowercase
---

`Oracle DataBase 21C` 계정 생성하는 방법입니다. 

---

- 환경
    
    Oracle DataBase 21C
    
    Window11 / 64bit 운영체제
    

---

1. cmd를 실행 후 sqlplus를 입력합니다.
    
    ```
    sqlplus
    ```
    
2. 사용자명 입력란에 system 을 적고, 비밀번호 입력란에 Oracle 설치 시 설정했던 비밀번호를 입력합니다. (입력할 때 안 보이는 게 정상입니다.)
    
    ```
    사용자명 입력 : system
    비밀번호 입력 : Oracle 설치할 때 설정했던 비밀번호
    ```
    
3. 그 다음 conn/as sysdba 라고 입력합니다.
    
    ```
    conn/as sysdba
    ```
    
4. Oracle 11g 에서는 바로 계정을 생성해도 되지만, Oracle 21C 부터는 계정을 생성하기 전에 alter session set “_ORACLE_SCRIPT”=true; 를 입력해야합니다. (이걸 적지 않으면 계정을 생성할 때 아이디 앞에 C##을 적어줘야 합니다.)
    
    ```
    alter session set “_ORACLE_SCRIPT”=true;
    ```
    
5. 계정을 생성합니다.
    
    ```
    create user 아이디 identified by 비밀번호;
    ```
    
6. 권한을 부여합니다.
    
    ```
    grant connect, resource, dba to 아이디;
    ```
    
7. commit 합니다.
    
    ```
    commit;
    ```