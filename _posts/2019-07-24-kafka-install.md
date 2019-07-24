---
title: "Windows 환경에서 Kafka 설치 및 실행"
date: 2019-07-24 08:42
categories: Java/Framework
---

목차  
>+ [1. 카프카 설치](#카프카-설치)  
>+ [2. 카프카 설정](#카프카-설정)  
>+ [3. 카프카 실행](#카프카-실행)  
>    * [3 - 1. 주키퍼 실행](#주키퍼-실행)  
>    * [3 - 2. 카프카 실행](#카프카-실행)  
>+ [4. 카프카 예제](#카프카-예제)
>    * [4 - 1. 카프카 토픽 생성](#카프카-토픽-생성)
>    * [4 - 2. 카프카 토픽 리스트 조회](#카프카-토픽-리스트-조회)
>    * [4 - 3. 카프카 consumer 실행)(#카프카-consumer-실행)
>    * [4 - 4. 카프카 producer 실행](#카프카-producer-실행)
>+ [5. 메이븐과 이클립스를 이용한 카프카 클러스터 구축](#메이븐과-이클립스를-이용한-카프카-클러스터-구축)
>    * [5 - 1. 프로젝트 생성](#프로젝트-생성)
>    * [5 - 2. dependency 추가](#dependency-추가)
>    * [5 - 3. 컨슈머 작성)(#컨슈머-작성)
>    * [5 - 4. producer 작성](#producer-작성)
>    * [5 - 5. 실행](#실행)

  
  
## 카프카 설치

   
[링크 클릭](https://kafka.apache.org/downloads) -> 공식 다운로드 사이트 or 미러 사이트 에서 카프카 압축 파일 다운로드 -> 압축 해제 ->  
   
![kafka-install-1](https://user-images.githubusercontent.com/50867723/61767436-381aa400-ae1f-11e9-8300-5dc1df67d272.png)  
   
 
## 카프카 설정
   
설치 경로확인 ->   
디렉토리 config로 이동 ( ex) C:\dev\kafka_2.11-1.1.0\config) ->   
server.properties 파일 텍스트 편집기로 오픈 ->  
log.dirs=/tmp/kafka-logs 를 카프카 설치 경로로 변경 ->  
>ex ) log.dirs=C:\\dev\\kafka_2.11-1.1.0\\logs  
   
![kafka-install-2](https://user-images.githubusercontent.com/50867723/61767445-3fda4880-ae1f-11e9-8147-7113094881a4.png)  
   
![kafka-install-3](https://user-images.githubusercontent.com/50867723/61767456-48328380-ae1f-11e9-8ae3-feebf64542c4.png)  

## 카프카 실행
   
### 주키퍼 실행
   
%주키퍼 설치 및 설정은 [Windows 환경에서 Zookeeper 설치 및 실행](https://taemin11.github.io/java/framework/Zookeeper-first/) 참고
Zookeeper 실행 ->
   
### 카프카 실행
   
주키퍼 cmd창 유지한 채로 새로운 cmd 실행 ->   
kafka 설치 경로로 이동 ->   
>ex) cd C:\dev\kafka_2.11-1.1.0   
bin\windows\kafka-server-start.bat config\server.properties 입력 ->   
  
![kafka-install-4](https://user-images.githubusercontent.com/50867723/61767464-4ec0fb00-ae1f-11e9-8cb9-ce56fce75288.png)  
   
## 카프카 예제
   
### 카프카 토픽 생성
   
주키퍼, 카프카 실행한 상태에서 새로운 cmd 실행 ->   
kafka 설치 경로로 이동 ( ex) cd C:\dev\kafka_2.11-1.1.0) ->   
bin\windows\kafka-topics.bat --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic test20190715 입력   
   
![kafka-install-5](https://user-images.githubusercontent.com/50867723/61767476-54b6dc00-ae1f-11e9-80d8-9f711cd8faf2.png)  
   
### 카프카 토픽 리스트 조회
   
bin\windows\kafka-topics.bat --list --zookeeper localhost:2181 입력
  
![kafka-install-6](https://user-images.githubusercontent.com/50867723/61767480-584a6300-ae1f-11e9-9c9f-d1f5fbcd6051.png)  
   
### 카프카 consumer 실행
  
bin\windows\kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic test20190715 입력   
   
![kafka-install-7](https://user-images.githubusercontent.com/50867723/61767485-5b455380-ae1f-11e9-9a79-160200f53d9f.png)  

### 카프카 producer 실행
  
주키퍼, 카프카, 컨슈머 cmd창 유지한 채로 새로운 cmd 실행 ->  
kafka 설치 경로로 이동 ( ex) cd C:\dev\kafka_2.11-1.1.0) ->  
bin\windows\kafka-console-producer.bat --broker-list localhost:9092 --topic test20190715 입력->  
메시지 입력 ->  
  
![kafka-install-8](https://user-images.githubusercontent.com/50867723/61767488-5da7ad80-ae1f-11e9-9122-1448a347fc9f.png)  
  
consumer 메시지 수신 확인
  
![kafka-install-9](https://user-images.githubusercontent.com/50867723/61767490-60a29e00-ae1f-11e9-90cf-8ad31295955a.png)  
  
  
## 메이븐과 이클립스를 이용한 카프카 클러스터 구축
  
### 프로젝트 생성
  
이클립스 실행 -> maven project 생성 ->   
  
![kafka-install-10](https://user-images.githubusercontent.com/50867723/61767495-639d8e80-ae1f-11e9-9286-6757d570a644.png)  
  
### dependency 추가
   
pom.xml에 의존성 추가 -> 저장 ->  

		<dependency>
			<groupId>org.apache.kafka</groupId>
			<artifactId>kafka-clients</artifactId>
			<version>1.1.0</version>
			</dependency>
			<dependency>
			    <groupId>org.apache.kafka</groupId>
			    <artifactId>kafka-streams</artifactId>
			    <version>1.1.0</version>
			</dependency>
			<dependency>
			    <groupId>org.apache.kafka</groupId>
			    <artifactId>kafka_2.11</artifactId>
			    <version>0.8.2.1</version>
			</dependency>

  
### consumer 작성
  
>consumer code와 producer code는 황준일님 블로그에서 [https://kafka.apache.org/quickstart](https://kafka.apache.org/quickstart) 퍼왔습니다.


package com.test.kafka.meta;
import org.apache.kafka.clients.consumer.ConsumerRecord;
import org.apache.kafka.clients.consumer.ConsumerRecords;
import org.apache.kafka.clients.consumer.KafkaConsumer;
import java.util.Arrays;
import java.util.Properties;

		public class Consumer {

		    public static void main(String[] args) {
			Properties configs = new Properties();
			// 환경 변수 설정
			configs.put("bootstrap.servers", "localhost:9092");     // kafka server host 및 port
			configs.put("group.id", "testGroup");                // group id 설정
			configs.put("key.deserializer", "org.apache.kafka.common.serialization.StringDeserializer");    // key deserializer
			configs.put("value.deserializer", "org.apache.kafka.common.serialization.StringDeserializer");  // value deserializer
			KafkaConsumer<String, String> consumer = new KafkaConsumer<String, String>(configs);    // consumer 생성
			consumer.subscribe(Arrays.asList("testTopic"));      // topic 설정
			while (true) {  // 계속 loop를 돌면서 producer의 message를 띄운다.
			    ConsumerRecords<String, String> records = consumer.poll(500);
			    for (ConsumerRecord<String, String> record : records) {
				String s = record.topic();
				if ("testTopic".equals(s)) {
				    System.out.println(record.value());
				} else {
				    throw new IllegalStateException("get message on topic " + record.topic());
				}
			    }
			}   
		    }

		}
  
  
### producer 작성
  

		package com.test.kafka.meta;

		import java.io.IOException;
		import java.util.Properties;
		import org.apache.kafka.clients.producer.KafkaProducer;
		import org.apache.kafka.clients.producer.ProducerRecord;

		public class Producer {

		    public static void main(String[] args) throws IOException {
			// producer properties 설정
			Properties configs = new Properties();
			configs.put("bootstrap.servers", "localhost:9092"); 										// kafka host 및 server 설정
			configs.put("retries", "1"); 																// 메시지 전송 실패 시 재전송
			configs.put("key.serializer", "org.apache.kafka.common.serialization.StringSerializer");	// serialize 설정
			configs.put("value.serializer", "org.apache.kafka.common.serialization.StringSerializer");	// serialize 설정

			// producer 생성
			KafkaProducer<String, String> producer = new KafkaProducer<String, String>(configs);

			// message 전달
			String v = "{\"logs\": "
					+ "[{\"test1\": \"val1\"},"
					+ "{\"test2\": \"val2\"}],"
					+ "\"version\":1}\n";
			producer.send(new ProducerRecord<String, String>("testTopic", v));


			// 종료

			producer.close();
		    }

		}
  

### 실행

주키퍼 실행 -> 카프카 실행 -> 컨슈머 실행 -> 프로듀서 실행
  
[!kafka-install-11](https://user-images.githubusercontent.com/50867723/61768455-7e253700-ae22-11e9-8342-66ded6327086.png)  


