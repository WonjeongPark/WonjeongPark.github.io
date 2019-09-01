---
layout: post
title:  "Stack&Queue_Algorithm"
date:   2019-08-10
excerpt: "Stack&Queue_Algorithm"
image: "/images/Stack&Queue.png"
---

# 스택, 큐(Stack and Queue)
## 스택
자료의 입력과 출력이 한 방향으로 제한된 자료구조.<br>
후입선출 : LIFO(Last In First Out) - 제일 마지막으로 입력된 데이터가 제일 먼저 삭제되는 구조.<br>
```
Top : 스택으로 할당된 기억공간에서 가장 마지막으로 삽입된 자료가 기억된 위치 (스택포인터)
Bottom : 스택의 가장 아래부분<br>
```
push() : 자료넣기,입력 - Top으로 자료를 입력하고 스택포인터 1 증가.<br>
pop() : 자료빼기, 삭제 - Top위치의 자료를 출력하고 Top, 즉 스택포인터를 1 감소.<br>
<br>
EX) 콜스택(Call Stack) - 함수호출 등으로 점프하게 되는 경우 돌아오는 주소를 저장<br><br>

>예외처리
저장된 데이터가 없어서 pop()을 하여 생기는 오류(=스택포인터의 값이 0) -> Stack Underflow<br>
스택의 크기만큼 저장된 데이터에 push()를 하여 생기는 오류(스택포인터 값>스택의크기) -> Stack Overflow

<br>

`단점`- 후입선출로 인한 우선순위 관련 문제 발생 가능, 계속 자료가 입력되면 처음 입력된 데이터가 오래 잔류하는 경우 등<br>


## 큐
자료의 입력과 출력을 한쪽 끝으로 제한된 자료구조.<br>
선입선출 : FIFO(First In First Out) - 맛집 대기 줄과 같이 먼저 입력된 데이터가 먼저 삭제되는 구조.<br>
`shift()와 unshift() 혹은 put()과 get()`<br>
혹은 삽입연산을 Enqueue, 삭제연산을 Dequeue라고 한다.<br><br>
EX) OS스케쥴러, 스레트, 윈도우 메세지큐<br><br>

직선 형태의 큐에서 처음 들어온 데이터가 삭제되면 다른 데이터들을 차례로 앞으로 당겨줘야 한다.<br>
많은 데이터가 존재하는 경우에는 연산에 시간이 걸릴 수 있다.<br>


>위의 문제점의 해결방안으로 나온 것이 `원형 큐`, `순환 큐`, `환영 큐` 로 불리는 방법이다.<br>
배열을 직선이 아닌 원형으로 보는 방법이다.<br>
![QueueEx](https://raw.githubusercontent.com/WonjeongPark/whatIThink/0168aefa77a81c2ebceb4cd0d1c6d5ab4183488e/%EC%9B%90%ED%98%95_%ED%81%90.png)

```
Front(Head) - 자료가 출력될 때 삭제되는 부분 ( -1의 경우 자료 끝으로)<br>
Rear(Tail) - 자료가 입력될 때 추가되는 부분 ( 0은 자료의 끝)<br>
```

<br>
`단점` - 자료 입력 후 데이터를 계속 삭제하면 Rear와 Front가 만나게 되어 공백큐이지만 overflow 현상 발생 (메모리낭비)

## Double-ended queue (데큐, 덱)
큐와 스택의 장점을 합쳐놓은 개념이다.<br>
양쪽 끝에서 자료의 삽입과 삭제가 모두 가능한 자료구조이다.<br>
(두 개의 포인터를 사용하여 양쪽에서 삽입과 삭제 발생 가능)<br>
```
입력을 한쪽 끝으로만 가능하도록 설정한 데크 - 입력제한데크(scroll)
출력을 한쪽 끝으로만 가능하도록 설정한 데크 - 출력제한데크(Shelf)
```