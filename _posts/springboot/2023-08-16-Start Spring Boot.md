---
title: "[mac OS] SpringBoot Toy Project 준비하기"
categories:
    - SpringBoot

tags:
    - mac
    - SpringBoot
    - h2
    - java

toc: true
toc_sticky: trues
toc_label: "Start SpringBoot"
toc_icon: "tasks"
---

📌 작성자 개발 환경 Mac M1 PRO
{: .notice--primary}

# MacOS 환경에서 SpringBoot Toy Project 준비하기
이 게시글은 macOS 환경에서 Spring Boot 프로젝트를 설치하고 toy project 를 진행하는 과정을 쉽게 따라할 수 있도록 설명합니다.

## 1. Java 설치 확인
Spring Boot 는 Java로 개발되므로, 먼저 Java 가 설치되어 있는지 확인해야 합니다. 
```bash
java -version
```
자바 설치 가이드 : <https://hanmingi.github.io/mac/install-Adoptium-JDK/>


## 2. Spring Initializr 사용하기
### - Spring Initializr 란?
Spring Initializr는 Spring Boot 기반의 프로젝트를 쉽게 생성할 수 있는 웹 기반 도구입니다.

이를 통해 프로젝트의 구조, 종속성 및 설정을 선택하여 초기 설정 단계를 간소화 할 수 있습니다.

### - 주요기능
* 프로젝트 기본 설정 : 프로젝트의 이름, 그룹, 패키지 명 등을 설정할 수 있습니다.
* 종속성 관리 : 필요한 Spring Boot 시작 종속성을 선택하여 추가할 수 있습니다.
* 빌드 설정 : Maven 또는 Gradle 과 같은 빌드 도구를 선택하고 설정할 수 있습니다.
* 메타 데이터 설정 : 프로젝트의 부가 정보를 입력할 수 있습니다.

### - 사용법
1. 웹 브라우저에서 **<https://start.spring.io/>** 주소로 접속합니다.
2. 화면 상단의 옵션에서 다음을 설정합니다.
   * Project : 프로젝트 유형 선택 ( Maven, <span style="color:red"> Gradle </span>) // 필자는 Gradle로 진행
   * Language : 프로젝트 언어 선택 ( <span style="color:red"> Java</span>, Kotlin, Groovy) // 필자는 Java로 진행
   * Spring Boot : Spring Boot 버전 선택 // 필자는 현 시점에서 제일 안정적인 <span style="color:red">3.1.2</span> 선택
3. 프로젝트 그룹과 아티팩트 정보를 입력합니다.
4. Dependencies 옵션에서 필요한 Spring Boot 시작 종속성을 검색하고 선택합니다.
   * Spring Web : 웹 프로젝트
   * Spring Data Jpa : 데이터 베이스 연동하기 위해 추가
   * H2 Database : 테스트용 데이터 베이스인 h2 추가
   * Thymeleaf : 템플릿 엔진 추가
   * Lombok : getter, setter 생성자 등을 만들어주는 lombok 추가

위까지의 설정이 완료 되었으면 아래의 사진과 같은 설정완료 되어 프로젝트를 생성할 준비가 완료 되었습니다.

<img width="1509" alt="스크린샷 2023-08-16 11 58 12" src="https://github.com/hanmingi/hanmingi.github.io/assets/22022390/f2597962-8660-4be4-ae4a-d114f1147d0f">

이후 **Generate** 을 통해 프로젝트 내려받게 되면 알집 형태로 내려받게 되는데 압축을 해제 한 후 인텔리제이에서 프로젝트를 열면 toy project 를 진행할 준비가 완료 되었습니다.

