---
layout: post
title:  "Howto 빌드 방법"
date:   2019-08-18
excerpt: "HOWTO PROJECT"
image: "/images/howtoHomepage.png"
---

#### <center>Main homepage</center>

### 빌드, 실행방법

1. git 설치&원격저장소 로컬로 내려받기<br>
`git clone  https://github.com/WonjeongPark/howto.git`<br>
2. nodejs 설치하기<br>
`https://nodejs.org/ko/ -> 다운받기`<br>
3. DB 설치하기<br>
`https://www.mysql.com/ ->  MySQL Installer 다운받기` <br>
username: 'root',<br>
password: 'howto@@'<br>
4. 데이터베이스&Table 생성<br>
시작 - MySQL Server 5.7  - Command Line Client 실행<br>
`CREATE DATABASE ex_nodejs_db`<br>
`USE ex_nodejs_db`<br>

```
>CREATE TABLE `users` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `loginID` varchar(45) NOT NULL,
  `loginPW` varchar(45) NOT NULL,
  `name` varchar(255) DEFAULT NULL,
  `gym` varchar(255) DEFAULT NULL,
  `gender` varchar(255) DEFAULT NULL,
  `career` varchar(255) DEFAULT NULL,
  `bodypart` varchar(255) DEFAULT NULL,
  `playerSource` varchar(255) DEFAULT NULL,
  `count` int(11) DEFAULT NULL,
  `Num` int(11) DEFAULT NULL,
  `createdAt` datetime NOT NULL DEFAULT CURRENT_TIMESTAMP,
  `updatedAt` datetime NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=14 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;
```

```
>CREATE TABLE `dates` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `users_id` int(11) NOT NULL,
  `dates` datetime DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `fk_dates_users1` (`users_id`),
  CONSTRAINT `fk_dates_users1` FOREIGN KEY (`users_id`) REFERENCES `users` (`id`)
  ON DELETE CASCADE ON UPDATE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=25 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;
```

5. 데이터 집어넣기<br>

```
INSERT INTO users (loginID, loginPW, name, gym, gender, career, bodypart, playerSource, count, Num)
VALUES('howto1','howto1','박원정','스포스포잠실점','여성','1년~2년','목','http://media.w3.org/2010/05/bunny/trailer.mp4',10,3);
```

```
INSERT INTO users (users_id, dates) VALUES (1, '2019-05-12 12:34:56')
INSERT INTO users (users_id, dates) VALUES (1, '2019-05-17 12:34:56')
INSERT INTO users (users_id, dates) VALUES (1, '2019-06-24 12:34:56')
```

또는 localhost:3000/SignUp을 통해 등록<br>


6. 모듈 설치하기<br>
git bash실행<br>
`cd howto -> npm install -> node server.js`<br>
`cd howto/client -> npm install -> npm start`<br>
`localhost:3000` 접속