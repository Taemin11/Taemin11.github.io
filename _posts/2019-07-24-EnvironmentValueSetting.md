---
title: "Windows JAVA 환경 변수 설정"
date: 2019-07-24 17:01
categories: Java/Framework
---

목차  
>+ [1. 주키퍼 환경변수 설정](#주키퍼-환경변수-설정) 
>+ [2. 자바 환경변수 설정](#자바-환경변수-설정)  
 


  
  
## 주키퍼 환경변수 설정

   
제어판 -> 시스템 및 보안 -> 시스템 -> 고급 시스템 설정 -> 환경 변수 ->   
  
![EVset-1](https://user-images.githubusercontent.com/50867723/61775640-4626ef80-ae34-11e9-8c00-5fc13a983a77.png)  
  
사용자 변수 새로 만들기 -> 변수 이름에 ZOOKEEPER_HOME, 변수 값에 zookeeper 설치 경로 입력 후 확인 ->
   
![EVset-2](https://user-images.githubusercontent.com/50867723/61775672-5343de80-ae34-11e9-91fa-213e2c26ea3c.png)  
  
시스템 변수 Path 클릭 -> 편집 ->   
![EVset-3](https://user-images.githubusercontent.com/50867723/61775685-58a12900-ae34-11e9-8a8d-9aed45b76aec.png)  
  
새로 만들기 -> %ZOOKEEPER_HOME%\bin 입력 -> 확인 ->  
  
![EVset-4](https://user-images.githubusercontent.com/50867723/61775693-5d65dd00-ae34-11e9-911b-69e55b04c625.png)  
  
  
## 자바 환경변수 설정
   
제어판 -> 시스템 및 보안 -> 시스템 -> 고급 시스템 설정 -> 환경 변수 ->  
사용 자 변수 새로 만들기 -> 변수 이름 CLASSPATH, 변수 값 %classpath% 입력 -> 확인 -> 다시 새로 만들기 -> 변수 이름 JAVA_HOME , 변수 값에 java 경로 입력 [jdk 추천] ->   
  
![EVset-5](https://user-images.githubusercontent.com/50867723/61775708-65258180-ae34-11e9-8785-f4c950fc8377.png)  
  
![EVset-6](https://user-images.githubusercontent.com/50867723/61775715-69ea3580-ae34-11e9-919d-6e909a384be7.png)  
  
시스템 변수 Path 클릭 -> 편집 -> 새로 만들기 -> %JAVA_HOME%\bin 입력  
  
![EVset-7](https://user-images.githubusercontent.com/50867723/61775723-6e165300-ae34-11e9-9229-ce42ee720d29.png)  
