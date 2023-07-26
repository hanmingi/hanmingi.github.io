---
title: "[For MAC] homebrew 설치하기"
categories:
    - mac

tags:
    - mac
    - install package
    - install
    - homebrew

toc: true
toc_sticky: true
toc_label: "For MAC"
toc_icon: "tasks"
---

📌 작성자 개발 환경 Mac M1 PRO
{: .notice--primary}

# Install Homebrew
homebrew는 macOS 운영체제에서 소프트웨어 패키지를 쉽게 설치하고 관리하는 명령줄 도구입니다.

아래 가이드에 따라 HomeBrew를 설치할 수 있습니다.

---

## 1. Xcode Command Line Tools 설치
Homebrew를 설치하기 전에 Xcode Command Line Tools를 설치해야 합니다. 터미널에서 아래 명령어를 실행하여 설치합니다.

```bash
xcode-select --install
```

---


## 2. Homebrew 설치

터미널을 열고 아래 명령어를 실행하여 Homebrew를 설치합니다.

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

설치 스크립트가 실행되면, 시스템 패스워드를 입력하고 설치를 진행하세요. 설치가 완료되면 Homebrew가 준비된 것입니다.

---

## 3. Homebrew 경로 설정

Homebrew로 설치한 패키지들을 사용하려면, Homebrew가 제공하는 경로를 환경 변수에 추가해야 합니다. 아래 명령어를 실행하여 환경 변수를 설정합니다.

```bash
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.zprofile
eval "$(/opt/homebrew/bin/brew shellenv)"
```

---

## 4. 설치 확인

Homebrew가 제대로 설치되었는지 확인해봅니다. 터미널에서 아래 명령어를 실행하여 Homebrew 버전을 출력합니다.

```bash
brew --version
```
<img width="524" alt="image" src="https://github.com/hanmingi/hanmingi.github.io/assets/22022390/622c3dd4-39bf-4f04-ac04-e14335559c21">


버전이 출력되면 Homebrew가 성공적으로 설치된 것입니다.

---

## 5. 패키지 설치

이제 Homebrew를 사용하여 원하는 패키지를 설치할 수 있습니다. 예를 들어, `wget` 패키지를 설치해보겠습니다.

```bash
brew install wget
```

설치가 완료되면 `wget` 명령어를 사용하여 파일을 다운로드할 수 있습니다.

---

## 6. 주요 명령어
### 6.1. 프로그램 설치관련
```bash
brew update                # brew를 최신 버전으로 업데이트

brew search [패키지명]        # 설치 가능한 프로그램 검색

brew install [패키지명][@버전] # 프로그램 설치 @특정버전

brew update [패치지명]        # 패키지 업데이트

brew upgrade               # 모든 패키지 업그레이드
```

### 6.2. 정보확인
```bash
brew list                 # 설치된 프로그램 목록

brew info [패키지명]        # 패키지 정보보기

brew outdated             # 업그레이 필요한 프로그램 찾
```

### 6.3. 삭제
```bash
brew cleanup [패키지명]     # 최신버전 이외에 모두 삭제

brew uninstall [패키지명]   # 특정 패키지 삭제
```

## 7. uninstall Homebrew
Homebrew를 제거하기 위해 터미널에서 아래 명령어를 실행합니다.

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/uninstall.sh)"
```

삭제 완료 후 ```/opt/homebrew``` 폴더 까지 제거하게 되면 homebrew를 통해 설치된 프로그램까지 모두 삭제됩니다.

