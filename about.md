---
layout: page
title: HowTo
description: About Howto website
sitemap:
    priority: 0.7
    lastmod: 2019-08-01
    changefreq: weekly
---
## HowTo Project
### 2019-03 ~ 현재
#### <center>Main homepage</center>
<a href="#" class="image main"><img src="/images/howtoHomepage.png" alt="" /></a>

> 개발툴: Visual Studio Code<br>
> 라이브러리 & 프레임워크: ReactJs, NodeJs(Express기반 REST API)<br>
> 언어: Html, css, Javascript<br>

> Front-end : HTML, CSS, Javascript, ReactJs<br>
> Back-end : NodeJs(Express기반 REST API), Mysql(sequelize)<br>
> <div class="actions">
	<a href="https://github.com/WonjeongPark/howto" class="button">HOWTO 개발계획서</a>&nbsp;&nbsp;<a href="https://docs.google.com/presentation/d/19S967ZQ7yASUOyzDys5l-D6k_L6AQt2WhODyO6SyT4M/edit?usp=sharing" class="button">HowTo 스토리보드</a>&nbsp;&nbsp;<a href="{{ "/blog/HowtoBuild" | absolute_url }}" class="button">Howto 빌드 방법보기</a>

<br>
### 개발 동기
개발을 잘 모르던 시절, 무작정 8시간 넘게 인강을 들으며 오랜 시간 앉아있다 보니 소화불량과 허리 통증이 생겼습니다.<br>
근본적인 해결을 위해 헬스장을 다니기 시작하였을 때, PT를 하고 싶지만 일부 트레이너들의 상담방식이 굉장히 영업적인 부분에<br> 치우쳐져 있고 그런 부분이 상당히 부담스럽게 다가왔습니다. 그때 이런 사이트가 있으면 좋겠다고 생각해 보았습니다.<br>

### ReactJs, WEB을 선택한 이유

1. ReactJS를 선택한 이유<br> 
HowTo를 개인 트레이너(trainer)와 수강생(trainee)의 중개 플랫폼이라는 콘셉트 아래 개발계획서 작성 당시 Profile, Video 등 같거나 비슷한 부분이 포함된 네임카드들이 반복되는 것이 효율적이라고 생각했고 이 부분이 React의 Component 부분과 잘 어울릴 것이라고 생각하였습니다.<br> 
2. WEB을 선택한 이유
헬스장이나 운동업계 시스템이 일별, 월별 등록시스템이 주를 이루고, 그에 따라 그때그때 발생되는 프로모션과 관련된 배너 등의 즉각적인 반영을 위해서 서버에 변경사항을 업데이트하고 또 클라이언트에서 요청이 쉬운 WEB을 선택하였습니다.

## Redux, Mobx, Context API 등을 사용하지 않은 이유

React에서 프로젝트의 규모가 커질 수록 상태관리는 중요하고 복잡해집니다.<br>
Redux, Mobx 그리고 Context API까지 좋은 라이브러리가 생겨난 이유라고 생각합니다.<br>
<strong>하지만 모든 프로젝트에 필수적인 것은 아니라고 생각합니다.</strong><br><br>
번거롭고 혹은 복잡하더라도 가장 기본적인 방법으로 React에서 상태관리를 경험해야<br>
추후에 위에서 언급한 상태관리 라이브러리를 적용하게 되더라도<br>
전반적인 프로세스을 이해하고 더 효율적인 적용을 할 수있다고 생각합니다.<br>
그래서 HowTo에는 상태관리 라이브러리를 사용하지 않았습니다.<br>
이후에 Redux, Redux-thunks, Redux-saga등 을 적용한 프로젝트를 진행해보니<br>
올바른 선택이었다고 느끼고 있습니다.<br>
이에 관한 포스팅은 추후에 업데이트 될 예정입니다.<br>

## howto 프로젝트 중 에러 해결 -Lifecycle
<a href="{{ "/blog" | absolute_url }}" class="button">읽어보기</a>

## Howto 이미지 

<img src="/images/howto/HomepageR.png" width="100%" alt="HomepageR"><br>
### HomePage
1. 메뉴<br>
2. 로그인, 회원가입 버튼 -> 각 페이지 이동<br>
3. 트레이너찾기 버튼 -> 로그인화면 이동<br>
(로그인되어있다면 회원유형에따라 수강생-> 트레이너페이지 / 트레이너 -> 수강생목록페이지 이동예정)<br>

<img src="/images/howto/LoginR.png" width="100%" alt="LoginR"><br>
### Login
1. 로그인, 회원가입 버튼<br>
2. 아이디, 비밀번호 입력 후 로그인버튼<br>
(회원유형에따라 수강생-> 트레이너페이지 / 트레이너 -> 수강생목록페이지 이동예정)<br>
3. 회원가입 버튼 -> 회원가입폼 이동<br>

<img src="/images/howto/Form1.png" width="100%" alt="Form1"><br>
<img src="/images/howto/Form2R.png" width="100%" alt="Form2R"><br>
### Form(Trainer Version)
1. MultipleDatePicker를 이용하여 원하는 날짜 여러개 선택가능(아래 이미지)<br>
2. 직접입력 or 버튼 이용 횟수조절<br>
3. 회원가입 이동<br>
(회원유형에따라 수강생-> 트레이너페이지 / 트레이너 -> 수강생목록페이지 이이동예정동)<br>

<img src="/images/howto/Form_dates2.png" width="100%" alt="Form_dates2"><br>
### Form -dates
1. MultipleDatePicker를 이용하여 원하는 날짜 여러개 선택 가능<br>
2. 선택 시점의 날짜 포함 이후 날짜만 선택 가능<br>

<img src="/images/howto/TrainerListR.png" width="100%" alt="TrainerListR"><br>
### TrainerList
1. 나의 프로필, 로그아웃버튼 예정<br>
2. 클릭시 4번과 같이 날짜보여지기<br>
3. 트레이너에게 메일 보내기<br>
4. MultipleDatePicker를 이용한 날짜 리스트 보여지기(2개이상일 경우 스크롤생성)<br>
5. Trainer 회원가입시 등록한 간단 운동 비디오 보여지기<br>
6. 영상 즐겨찾기 예정 및 해당 트레이너에게 메일보내기<br>
7. 비디오리스트부분 개별 스크롤<br>