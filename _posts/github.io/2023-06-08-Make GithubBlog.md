---
title: "[GitHub.io] GitHub [블로그 생성부터 테마 적용까지] - Mac M1 Pro"
categories:
    - github.io

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

📌 작성자 개발 환경 </br>
OS : Mac M1 PRO </br>
SHELL : zsh
{: .notice--primary}

## [01] Github Repository 생성
먼저 Github Blog를 사용하기 위해선 <b>[ID].github.io</b> 형태의 Repository를 생성해야한다.
<img width="765" src="https://github.com/hanmingi/hanmingi.github.io/assets/22022390/d145ef39-9b81-4bbc-9527-0bf5632865be">
[필자는 이미 Repository가 존재하기 때문에 에러가 발생한다.]

### - 생성한 Repo를 Local로 복사한다.
Repo를 로컬로 복사하는 방법은 크게 두가지가 있다. </br>
1. git clone 명령어 사용
2. zip 으로 다운로드 후 압축 해제

```
단, zip 으로 다운로드 하는 방법은 git이 자동으로 본인의 repo와 연결되지 않기 때문에 git clone을 사용을 추천한다.
```

터미널을 연 후 아래의 명령어를 입력하여 본인이 만든 Repo를 가져온다.
```terminal
git clone https://github.com/[userid]/[userid].github.io.git
```

여기까지 완료 되었다면 본인이 선택한 테마를 적용해보자.

## [02] Github Blog Theme
Github Blog 테마를 적용하기 위해선 ruby와 jekyll를 설치해야한다. </br>

맥은 기본적으로 시스템 ruby를 사용하고 있다. </br>

##### - 루비 버전확인 명령어
```
ruby -v
```
