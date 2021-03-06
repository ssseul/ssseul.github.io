---
title: spring programming chapter 1
layout: post
---
# Spring Programming Chapter 1 정리
---------------------------------------------------
Spring Programming의 Chapter 1 에서 중요한 부분 정리

# Chapter 1

## 스프링 프레임워크

스프링 프리엠워크는 일반 사용자를 위한 웹 기반 어플리케이션에서 부터 기업 환경의 어플리케이션 까지 다양한 영역에서 사용되며, 스프링 팀(http://spring.io/team)은 주요 모듈의 다양한 프로젝트 개발을 진행하며, 이를 통해 개발자들에게 효율적으로 어플리케이션을 개발할 수 있도록 하고 있음.

### 스프링 프로젝트 목록

| 프로젝트 | 설명 |
| :-----: | :--- |
| 스프링 프레임워크(Spring Framework) | 스프링을 이용해서 어플리케이션을 개발할 때 기반이 되는 프레임워크이며, 핵심 기능인 DI와 AOP 기능을 제공한다. 웹 어플리케이션을 개발할 때 사용하는 스프링 MVC, 스프링 ORM 등의 기능도 스프링 프레임워크에 포함되어 있다. |
| 스프링 데이터(Spring Data) | 데이터 연동을 위한 단일 API를 제공하며, 이 API를 기반으로 JPA, MongoDB, Neo4j, Redis 등 RDBMS와 NoSQL과의 연동을 적은 양의 코드로 처리할 수 있도록 해준다. |
| 스프링 시큐리티(Spring Security) | 인증과 허가에 대한 기반 프레임워크 및 관련 모듈을 제공한다. 웹 어플리케이션을 위한 보안을 간단한 설정과 약간의 코드 구현으로 처리한다. |
| 스프링 배치(Spring Batch) | 배치 처리를 위한 기반 프레임워크를 제공해준다. 데이터 처리, 흐름 제어, 실패 재처리 등 배치 처리 어플리케이션이 필요로 하는 기능을 기본으로 제공한다. |
| 스프링 인터그레이션(Spring Integration) | 시스템 간의 연동을 위한 메시징 프레임워크를 보여준다. |
| 스프링 소셜(Spring Social) | 트위터, 페이스북 등 소셜 네트워크 연동을 위한 기능을 제공한다. |

### 스프링 프레임워크의 주요 모듈

스프링 프레임워크는 제공하는 기능에 따라 별도의 모듈로 분리 되어 있는데 트랜잭션과 관련 기능을 제공하는 모듈은 spring-tx 이며, 웹 개발과 관련된 기능을 제공하는 모듈은 spring-webmvc 이다. 각각의 모듈은 jar 파일로 제공되며, 한 모듈을 사용하려면 의존된 다른 모듈이 필요한 경우도 있으므로 같이 설정해 주어야 한다.

* 스프링의 주요 모듈 목록

|   프로젝트   | 설명 |
| :---------: | :--- |
| **spring-beans**   | 스프링 컨테이너를 이용해서 객체를 생성하는 기본 기능을 제공한다. |
| **spring-context** | 객체생성, 라이프사이클 처리, 스키마 확장 등의 기능을 제공한다. |
| **spring-aop** | AOP(**Aspect Oriented Programming**) 기능을 제공 |
| spring-web | REST 클라이언트, 데이터 변환 처리, 서블릿 필터, 파일 업로드 지원 등 웹 개발에 필요한 기반 기능을 제공한다. |
| spring-webmvc | 스프링 기반의 MVC 프레임워크이며, 웹 어플리케이션을 개발하는데 필요한 컨트롤러, 뷰 구현을 제공한다. |
| spring-websocket | 스프링 MVC에서 웹 ㅗ소켓 연동을 처리할 수 있도록 한다. |
| spring-oxm | XML과 자바 객체 간의 매핑을 처리하기 위한 API를 제공한다. |
| spring-tx | 트랜잭션 처리를 위한 추상 레이어를 제공한다. |
| spring-jdbc | JDBC 프로그래밍을 보다 쉽게 할 수 있는 템플릿을 제공한다. |
| spring-orm | 하이버네이트, JPA, MyBatis 등과의 연동을 지원한다. |
| spring-jms | JMS 서버와 메시지를 쉽게 주고 받을 수 있도록 하기 위한 템플릿, 어노테이션 등을 제공한다. |
| spring-context-support | 스케줄링, 메일 발송, 캐시 연동, 벨로시티 등 부가 기능을 제공한다. |

메이븐 프로젝트에서 모듈을 사용하려면 사용할 모듈명과 버전을 의존 설정에 추가해준다.

```xml
<dependencies>
 	<dependency>
 		<groupId>org.springframework</groupId>
		<artifactId>spring-webmvc</artifactId> <!-- 모듈명 -->
 		<version>4.0.4.RELEASE</version> <!-- 버전 -->
 	</dependency>
 	<dependency>
 		<groupId>org.springframework</groupId>
		<artifactId>spring-orm</artifactId> <!-- 모듈명 -->
 		<version>4.0.4.RELEASE</version> <!-- 버전 -->
 	</dependency>
</dependencies>
```
