---
title: Ruby on MacOS
date: 2022-03-19 08:48:00 +09:00 
categories: [MacOS, Ruby] 
tags: [setting]     # TAG names should always be lowercase
---

MacOS는 기본적으로 ruby가 아래 위치에 기본적으로 설치되어 있습니다.

`/System/Library/Frameworks/Ruby.framework/Versions/`

MacOS Catalina 버전 10.15 부터 위 기능은 더이상 활성화 되지 않습니다. 

아마 나중에는 삭제될 가능성도 있습니다.

Rbenv는 루비 버전 관리자입니다. 때문에, 여러 버전의 ruby 를 사용할 수 있습니다.

Rbenv는 사용자 디렉토리 아래에 설치되고 ( `~/.rbenv` ), 설치된 루비 버전은 아래 위치에 설치됩니다.(`~/.rbenv/versions`)

---

- 환경
    
    MacBook Pro(Intel Core)
    
    Monterey OS(Version 12.2.1)
    
    git version 2.32.0(Apple Git-132)
    

---

## First clone rbenv

터미널에 아래 명령을 입력합니다.

```
git clone https://github.com/rbenv/rbenv.git ~/.rbenv
```

## The execute

```
cd ~/.rbenv && src/configure && make -C src
```

- macOS가 catalina 이전이라면 아래 명령을 입력합니다.

```
echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bash_profile
```

- macOS가 catalina 이상이라면 아래 명령을 입력합니다.

```
echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.zshrc
```

## Execute

```
~/.rbenv/bin/rbenv init
```

## Open Nano editor

나노 에디터를 실행합니다.

- 기본 쉘이 Bash인 경우. (일반적으로 Catalina 이전의 MacOS 버전에 해당됩니다)

```
nano ~/.bash_profile
```

rbenv를 자동로드하려면 다음을 추가합니다.

```
eval "$(rbenv init -)"
```

ctrl-x, 저장하고 종료합니다. 

- 기본 쉘이 zsh 인 경우. (일반적으로 MacOS Catalina 및 그 이후에 해당됩니다)

```
nano ~/.zshrc
```

rbenv를 자동로드하려면 다음을 추가합니다.

```
eval "$(rbenv init - zsh)"
```

ctrl-x, 저장하고 종료합니다. 

## Execute

- 기본 쉘이 Bash인 경우. (일반적으로 Catalina 이전의 MacOS 버전에 해당됩니다)

```
source ~/.bash_profile
```

- 기본 쉘이 zsh 인 경우. (일반적으로 MacOS Catalina 및 그 이후에 해당됩니다)

```
source ~/.zshrc
```

## ruby build 설치(**Install ruby build , to install ,versions of ruby**)

```
mkdir -p "$(rbenv root)"/plugins
```

```
git clone https://github.com/rbenv/ruby-build.git "$(rbenv root)"/plugins/ruby-build
```

## rbenv 설치 확인(**Verify rbenv has been installed correctly**)

```
curl -fsSL https://github.com/rbenv/rbenv-installer/raw/main/bin/rbenv-doctor | bash
```

## 최신 안정 릴리즈 표시(**Show the lastest stable releases)**

```
rbenv install --list
```

## Install Ruby

```
rbenv install <Version>
```

## rbenv rehash

```
rbenv rehash
```

## 버전 확인(rbenv)

```
rbenv versions
```

## 전역 설정

```
rbenv global <Version>
```

## 버전 확인(Ruby)

```
ruby -v
```