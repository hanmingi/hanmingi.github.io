---
title: "[mac OS] H2 Database 설치"
categories:
- SpringBoot

tags:
- mac
- SpringBoot
- h2
- java

toc: true
toc_sticky: trues
toc_label: "Install H2 Database"
toc_icon: "tasks"
---

📌 작성자 개발 환경 Mac M1 PRO
{: .notice--primary}

# H2 Database 설치 (Mac OS)
H2 데이터베이스는 주로 개발 및 테스트 목적으로 사용되는 내장형 인메모리 데이터베이스입니다. 다양한 이유로 H2 데이터베이스를 사용하는 경우가 있습니다:

1. **가벼움과 빠른 실행**: H2 데이터베이스는 인메모리 데이터베이스로서 메모리 내에서 동작하므로 디스크에 데이터를 저장하거나 관리하지 않습니다. 따라서 데이터베이스 작업이 빠르며 가벼운 환경에서도 빠르게 실행됩니다.

2. **테스트 및 개발**: H2 데이터베이스는 개발 및 테스트 환경에서 주로 사용됩니다. 개발자들은 애플리케이션 개발 및 디버깅을 위해 내장형 데이터베이스를 사용하여 테스트 데이터를 쉽게 만들고 조작할 수 있습니다.

3. **통합 테스트**: H2 데이터베이스를 사용하면 통합 테스트 시에 실제 데이터베이스와의 연결을 설정할 필요 없이 내장 데이터베이스를 사용하여 테스트를 수행할 수 있습니다. 이로 인해 테스트 환경의 격리와 테스트 실행의 빠르고 예측 가능한 특성을 얻을 수 있습니다.

4. **임베디드 데이터베이스**: H2는 자바 애플리케이션 내에서 실행되기 때문에 추가적인 데이터베이스 서버 설치나 관리가 필요하지 않습니다. 애플리케이션과 함께 패키징되어 배포될 수 있으며, 사용자가 추가적인 설정 없이 애플리케이션을 실행할 수 있습니다.

5. **간단한 설정**: H2 데이터베이스는 단일 JAR 파일로 제공되며, 설정이 간단합니다. 이는 개발자들이 프로젝트를 시작할 때 빠르게 데이터베이스 환경을 구축할 수 있도록 도와줍니다.

6. **휴대성**: H2 데이터베이스는 파일 형태로도 사용 가능하여 프로젝트를 다른 환경으로 이동하거나 공유하기 쉽습니다.

그러나 주의할 점도 있습니다:

- H2 데이터베이스는 내장형 데이터베이스로서 성능적인 측면에서 다른 상용 데이터베이스 시스템보다는 한계가 있을 수 있습니다. 실제 운영 환경에서는 주의해야 합니다.
- 데이터베이스 내에 저장된 데이터는 애플리케이션을 재시작하면 초기화됩니다. 따라서 영속적인 데이터 저장이 필요한 경우에는 다른 데이터베이스 시스템을 고려해야 합니다.

따라서 H2 데이터베이스는 주로 개발 및 테스트 환경에서 사용되며, 경량한 구성과 빠른 실행 속도를 제공하여 빠르게 애플리케이션을 개발하고 테스트할 수 있는 장점을 가지고 있습니다.


## 1. H2 database download
h2 database 설치 링크 : <https://www.h2database.com/html/main.html>

아래 링크에서 zip 파일을 다운받습니다.

![스크린샷 2023-08-20 16 13 20](https://github.com/hanmingi/hanmingi.github.io/assets/22022390/76f33324-bfed-4df9-9c3b-e9ce765b5d62)

## 2. unzip

```bash
# 알집의 이름은 버전에 따라 다를 수 있음
unzip h2-2023-07-04.zip 
```

## 3. execute
압축을 해제하면 h2라는 디렉토리가 생깁니다. 하위 bin 디렉토리로 접근하여 sh 파일에 권한을 주고 실행시킵니다.

```bash
# bin 으로 이동
cd h2/bin

# 실행파일에 권한부여하기
chmod 755 h2.sh

# H2 실행
./h2.sh -webAllowOthers
```
* 쿼리시 Sorry, remote connections ('webAllowOthers') are disabled on this server 이런 메시지를 보지 않기 위해 h2 설치시 -webAllowOthers 옵션을 넣어줍니다.

## 4. web Console
h2.sh 를 실행하게 되면 아래 상태의 웹 콘솔 브라우저가 열립니다. 

Spring Boot 를 통해 미리 db 파일을 만들어 두었으면 해당 정보에 맞게 입력하고 **연결**을 누릅니다.

![image](https://github.com/hanmingi/hanmingi.github.io/assets/22022390/b3140a83-3a8c-4050-b008-0df599c0ee3e)

* 스프링부트 프로젝트 설정 중 일부

![image](https://github.com/hanmingi/hanmingi.github.io/assets/22022390/2f3eee38-7f4a-4cef-9add-96c8e0c9b76e)


## 5. Done
아래와 같이 접속되면 성공입니다.

![image](https://github.com/hanmingi/hanmingi.github.io/assets/22022390/9a33e82c-4c10-4315-8266-9cf6d268c3de)

다음글 에서는 Spring Boot 에서 H2와 Connection 을 맺어 CURD 에 대한 동작을 확인해 보겠습니다. 