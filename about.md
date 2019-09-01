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
> 프레임워크: ReactJs, NodeJs<br>
> 언어: Html, css, Javascript
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

### Lifecycle
```
state = {
  users : [{
        id:'',
        name: '',
        gym: '',
        gender: '',
        career:'',
        dates:[],
        dates:'',
        bodypart:'',
        playerSource:'',
        count:0,
        Num:0
  }]
};


  componentDidMount() {
    this.callBackendAPI()
      .then(res => {console.log(res);
        this.setState( 
        {users : res}
      )} )
      .catch(err => console.log(err));
  }
  callBackendAPI = async () => {
    const response = await fetch('/users');
    const body = await response.json();
    if (response.status !== 200) {
      throw Error(body.message) 
    }
    return body;
  };

  render() {
       ///
  ```

콜백함수를 이용하여 DB에 저장된 users를 불러와 state에 담으려는 TEST용 CODE이다.

  ```
  console.log(this.state.users )
  console.log(this.state.users[0]) //ok
  console.log(this.state.users[1]) //ok
  console.log(this.state.users[0].name) //ok
  console.log(this.state.users[1].name) // ERROR!!

//**
  // 0은 되고 1은 안되는 이유는 무엇인가!!!!
//**
  }
```
멘붕에 빠지는 오류였다. 콜백 함수는 잘 작동되고 users[0], users[1] 모두 아주 예쁜 Array로 콘솔 창에 등장했지만 <br>
문제는 users 배열 속 특정 객체를 불러오는 과정에서 users[0].name과 users[1].name의 결과가 다르게 나왔기 때문이다.<br>
이때까지 공부한 개념과는 전혀 다른 오류에 느꼈던 당황함은 아직도 생생하다.<br>
<br>
정답은 Lifecycle에 있었다.<br>
console.log는 콜백 함수인 ComponentDidMount 전, 후에 한 번씩 동작되기 때문에 콜백 함수 전에 실행되는<br>
console.log(this.state.users[1].name)는 undefind였던 것이다.<br>
console.log(this.state.users[0].name)이 오류가 아닌 이유는 state에 미리 정의해놓은 빈 users array에 걸려<br>
값이 없을지언정 undefind 오류를 던지지 않았기 때문이다.<br>
<br>
며칠 동안 나를 괴롭혔던 오류는 아주 간단하고 이미 알고 있던 Lifecycle에 관한 것이었다.<br>
미리 정리했던 <a href="{{ "/blog/LifecycleAPI" | absolute_url }}" >Lifecycle 정리 글</a>을 읽어보고 새로 노트를 기록해 두었다.<br>
<br>
이 과정에서 깨달은 것은 오류가 발생하면 구문 오류뿐 아니라 Lifecycle를 포함해서 지금 실행되는 화면과 데이터의 흐름을 다시 짚어보고 오류가 나올만한 곳을 되짚어봐야 한다는 것이다.<br>
또한 알고 있는 개념이 언제 어느 상황에서 정체를 숨기고 나타날지 모른다는 것.<br>
즉 `개념을 이해한다는 것`에서 `개발을 하며 오류를 해결하는 것`은 심화과정이라는 것이다<br>
적당한 개념 정리와 실제 적용, 그에 따른 정리를 하는 것은 성장의 지름길이다! <br>