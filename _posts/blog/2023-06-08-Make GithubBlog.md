---
title: "[BLOG] GitHub [블로그 생성부터 테마 적용까지] - Mac M1 Pro"
categories:
    - blog

tags:
    - minimal mistakes
    - jekyll
    - github
    - github.io

toc: true
toc_sticky: true
toc_label: "Make GitHub.io"
toc_icon: "rss"
---

📌 작성자 개발 환경 Mac M1 PRO / ZSH
{: .notice--primary}

## [01] Github Repository 생성
먼저 Github Blog를 사용하기 위해선 <b>[ID].github.io</b> 형태의 Repository를 생성해야한다.
<br><br>
<img width="765" src="https://github.com/hanmingi/hanmingi.github.io/assets/22022390/d145ef39-9b81-4bbc-9527-0bf5632865be">
<br>

<span style="color:LightCoral; font-size:80%">
위 사진은 이미 Repository가 존재하기 때문에 에러가 발생한다.
</span>


### [01-1] clone Repository
Repo를 로컬로 복사하는 방법은 크게 두가지가 있다.
1. git clone 명령어 사용
2. zip 으로 다운로드 후 압축 해제

```
단, zip 으로 다운로드 하는 방법은 git이 자동으로 본인의 repo와 연결되지 않기 때문에 git clone을 사용을 추천한다.
```
<br><br>
터미널을 연 후 아래의 명령어를 입력하여 본인이 만든 Repo를 가져온다.
```shell
git clone https://github.com/[userid]/[userid].github.io.git
```

여기까지 완료 되었다면 본인이 선택한 테마를 Github Blog에 적용한다.

## [02] Github Blog Theme
Github Blog 테마를 적용하기 위해선 ruby와 jekyll를 설치해야한다.

맥은 기본적으로 시스템 ruby를 사용하고 있다.

```shell
* 루비 버전확인 명령어
ruby -v
```

따라서 sudo를 통해 root 권한으로 실행하면 설치가 가능하지만 보안상의 이유로 추천하는 방법은 아니다.

#### [02-1] rbenv
rbenv라는 ruby version 관리자를 통해 여러 루비 버전을 확인 및 설치할 수 있다. <br>
시스템 루비를 사용하지 않고 rbenv를 사용하여 jekyll를 설치할 수 있다.

먼저 homebrew를 통해 rbenv를 설치한다.
```shell
$ brew install rbenv
```
<br>

rbenv가 설치 완료 되었다면 아래 명령어를 통해 버전을 확인해보자
```shell
$ rbenv versions
```

<br>
이제 jekyll 설치에 필요한 ruby를 설치한 rbenv를 사용하여 설치해보자

```shell
$ rbenv install 3.0.6   // 3.0.6 버전 설치
$ rbenv global 3.0.6    // 글로벌 버전 변경
```
<img width="568" alt="image" src="https://github.com/hanmingi/hanmingi.github.io/assets/22022390/8966c4f8-27a6-4287-8f51-f78721cac2e5">
<br>

<span style="color:LightCoral; font-size:80%">
위 사진은 3.0.6 버전을 설치한 후 global 설정 변경한 사진
</span>
<br><br>
위처럼 루비 버전을 확인해보면 system이 아닌 rbenv를 통해 설치한 루비 버전으로 변경되어있다.