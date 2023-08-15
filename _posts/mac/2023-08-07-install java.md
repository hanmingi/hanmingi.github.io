---
title: "[mac OS] Java 설치하기"
categories:
    - mac

tags:
    - mac
    - install package
    - install
    - java

toc: true
toc_sticky: true
toc_label: "macOS"
toc_icon: "tasks"
---

📌 작성자 개발 환경 Mac M1 PRO / ZSH
{: .notice--primary}

# 맥북에서 Homebrew를 통한 AdoptOpenJDK 8 설치 가이드

이 가이드는 맥북(Mac) 운영체제에 Homebrew를 사용하여 AdoptOpenJDK 8을 설치하는 방법을 설명합니다. 

AdoptOpenJDK는 오픈 소스 JDK(Java Development Kit) 구현체 중 하나로, 무료로 사용할 수 있으며 다양한 플랫폼에서 자바 애플리케이션을 개발하고 실행할 수 있습니다.

## 1. Homebrew 설치

Homebrew가 설치되어 있지 않다면 아래 링크를 통해 Homebrew를 우선 설치합니다.

Homebrew 설치 가이드 : <https://hanmingi.github.io/mac/install-homebrew/>

## 2. AdoptOpenJDK 8 설치

Homebrew를 사용하여 AdoptOpenJDK 8을 설치합니다. 터미널에서 다음 명령어를 실행합니다.

```bash
# Homebre 업데이트
brew update

# adoptOpenJDK/openjdk 추가
brew tap AdoptOpenJDK/openjdk

# 특정 버전 설치 <필자는 8 버전을 설치>
brew install --cask adoptopenjdk8
```

설치가 완료되면 **AdoptOpenJDK 8**이 맥os 에 설치되었습니다.

## 3. Java 버전 선택

macOS 에서는 기본적으로 설치된 Java 버전을 사용합니다. 

하지만 Homebrew로 설치한 AdoptOpenJDK를 사용하려면 Java 버전을 변경해야 합니다.

```bash
echo 'export JAVA_HOME_8=$(/usr/libexec/java_home -v1.8)' >> ~/.zshrc

echo 'export JAVA_HOME=$JAVA_HOME_8' >> ~/.zshrc

source ~/.zshrc
```

## 4. 설치 확인

AdoptOpenJDK 8이 제대로 설치되었는지 확인합니다.

```bash
java -version
```

위 명령어를 실행하면 현재 설정된 Java 버전 정보가 출력됩니다. 

정상적으로 AdoptOpenJDK 8이 설치되어 있는지 확인하세요.

맥북(Mac)에 Homebrew를 통해 AdoptOpenJDK 8이 설치되었습니다.

다른 버전을 설치할 시 **~/.zshrc** 에서 버전만 변경해주시면 됩니다.

## 5. 버전 변경
```bash
# 특정 버전 설치 <필자는 변경할 11 버전을 설치>
brew install --cask adoptopenjdk11

# 설정파일을 열어 버전 변경 준비
vi ~/.zshrc

# 해당 줄을 주석처리 하고 11버전을 추가한다.
# 주석처리
'export JAVA_HOME_8=$(/usr/libexec/java_home -v1.8)'

# 추가
echo 'export JAVA_HOME_11=$(/usr/libexec/java_home -v11)' >> ~/.zshrc

echo 'export JAVA_HOME=$JAVA_HOME_11' >> ~/.zshrc

source ~/.zshrc
```

위와 같이 JAVA_HOME 변수에 1.8 버전의 경로가 담겨있었지만 11 버전의 경로로 변경해주시면됩니다.