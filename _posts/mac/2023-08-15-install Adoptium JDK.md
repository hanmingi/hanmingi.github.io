---
title: "[mac OS] Java 설치하기 (Temurin)"
categories:
- mac

tags:
- mac
- install package
- install
- java
- Temurin

toc: true
toc_sticky: true
toc_label: "macOS"
toc_icon: "tasks"
---

📌 작성자 개발 환경 Mac M1 PRO / ZSH
{: .notice--primary}

# 맥북에서 Homebrew를 통한 Adoptium 8 설치 가이드

## 1. Adoptium vs AdoptOpenJDK
AdoptOpenJDK는 OpenJDK의 pre-built 바이너리 입니다.

이클립스 재단에서 어답티움(Adoptium) 프로젝트를 진행하면서 AdoptOpenJDK는 deprecate 되어 더이상 업데이트 되지 않습니다.

따라서 AdoptOpenJDK를 사용하고 있다면 Adoptium의 temurin 바이너리로 교체하는게 좋습니다.

homebrew tap의 경우 2021년 후반부터 adoptopenjdk는 업데이트 되지 않습니다.

## 2. Temurin Java로 교체 설치
```bash
# adoptopenjdk untap (cask로 설치한 사람들만 대상)
brew untap AdoptOpenJDK/openjdk

# adoptopenjdk 삭제
# 필자는 java 8과 11을 사용중이었음으로 8버전과 11버전 삭제
brew uninstall adoptopenjdk8
brew uninstall adoptopenjdk11

# 최신 버전
brew install --cask temurin

# 버전 관리
brew tap homebrew/cask-versions

# 특정 버전 설치
brew install --cask temurin8
brew install --cask temurin11

# Java 설치위치 확인
/usr/libexec/java_home -V

# Java 버전 확인
java -version
```