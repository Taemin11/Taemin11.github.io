---
title: "Windows 환경에서 Zookeeper 설치 및 실행"
date: 2019-07-24 08:42
categories: java frameworks
---

목차  
>+ [1. 주키퍼 설치](#주키퍼-설치)  
>+ [2. 주키퍼 설정](#주키퍼-설정)  
>+ [3. 주키퍼 실행](#주키퍼-실행)  
>    * [3 - 1. 명령 프롬프트로 실행](#명령-프롬프트로-실행)  
>    * [3 - 2. 실행이 안 될 경우](#실행이-안-될-경우)  

  
  
## 주키퍼 설치

   
[링크 클릭](http://www.apache.org/dyn/closer.cgi/zookeeper/) -> 공식 다운로드 사이트 or 미러 사이트 에서 zookeeper 압축 파일 다운로드 ->  
   
![zookeeper-install-1](https://user-images.githubusercontent.com/50867723/61754939-5a48fd80-adf0-11e9-8fcb-bb3ac0abd773.png)
   
압축 해제 ->   
%7zip을 이용하면 tar.gz 파일 압축해제가 쉽습니다. https://www.7-zip.org/download.html
   
![zookeeper-install-2](https://user-images.githubusercontent.com/50867723/61755010-a98f2e00-adf0-11e9-9b6a-a2da9cde7ae4.png)
   
## 주키퍼 설정
   
설치 경로확인 ->   
ex) C:\dev\zookeeper-3.4.14   
data 경로 생성 ->   
ex) C:\dev\zookeeper-3.4.14\data
   
![zookeeper-install-3](https://user-images.githubusercontent.com/50867723/61755589-4d79d900-adf3-11e9-9dc0-03876953b009.png)
   
C:\dev\zookeeper-3.4.14\conf 경로에 있는 zoo_sample.cfg 복사 붙이기 -> 복사본 이름 zoo.cfg로 변경 ->   
![zookeeper-install-4](https://user-images.githubusercontent.com/50867723/61755614-65515d00-adf3-11e9-9b51-cb20dd9e239d.png)
   
zoo.cfg를 notepad++ 나 메모장 같은 텍스트 편집기를 이용하여 오픈 -> data 경로 추가  
ex) dataDir=C:\dev\zookeeper-3.4.14\data
   
![zookeeper-install-5](https://user-images.githubusercontent.com/50867723/61755624-726e4c00-adf3-11e9-9e52-aeab18b4dee5.png)
   
## 주키퍼 실행
   
### 명령 프롬프트로 실행
   
시작 -> 검색 -> cmd 검색 후  ->zookeeper 다운로드 경로 ( cd {경로} ) 입력 -> zkServer.cmd 실행  
![zookeeper-install-6](https://user-images.githubusercontent.com/50867723/61755652-83b75880-adf3-11e9-934d-8836ed760e01.png)
   
### 실행이 안 될 경우

환경 변수 설정 

