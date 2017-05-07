# enjoy-diving Project
enjoy-diving 스쿠버 다이빙 로그 관리를 위한 개인 프로젝트

## 1. Stack
Server를 구성하고 있는 framework 및 library 정보

**JAVA JDK는 1.8**을 기본으로 사용

+ [Spring Boot](http://projects.spring.io/spring-boot/ "Spring Boot")
+ [Spring Security](http://projects.spring.io/spring-security/ "Spring Security")
+ [Spring Security OAuth2](https://projects.spring.io/spring-security-oauth/)
+ [Spring Session With Redis](https://docs.spring.io/spring-session/docs/current/reference/html5/guides/boot.html)
+ [Spring Cloud With AWS S3](http://cloud.spring.io/spring-cloud-aws/spring-cloud-aws.html)
+ [Spring Data JPA](http://projects.spring.io/spring-data-jpa/)
+ [Querydsl](http://www.querydsl.com/)
+ [MariaDB](https://mariadb.org/ "MariaDB")
+ [Thymeleaf](http://www.thymeleaf.org "Thymeleaf")
+ [Spring Test](http://docs.spring.io/spring-boot/docs/current/reference/html/boot-features-testing.html)
+ [Spring Security Test](http://docs.spring.io/spring-security/site/docs/current/reference/html/test-method.html)
+ [Gradle Build Tool](https://gradle.org)
+ [Docker](https://www.docker.com)

** ETC
+ [Logback](https://logback.qos.ch/)

### Version 정보

+ java : `1.8`
+ gradle wrapper : `3.3`
+ spring boot(web, jpa, security, validation, jdbc, devtools, test) : `1.5.2.RELEASE`
+ dependency-management-plugin : `1.0.1.RELEASE`
+ lombok : `1.16.14`
+ spring-security-test : `4.2.2.RELEASE`
+ spring-boot-starter-thymeleaf : `3.0.2.RELEASE`
+ h2 : `1.4.194`

## 2. Project 구성

### Gradle Multi Project
Build Tool은 [Gradle](https://gradle.org)을 이용 하며, Multi Project로 구성함으로써 Project Package를 재활용하여 중복되는 코들 줄이고, Project를 계층 또는 다양화할 수 있도록 설계

### Project 구성

* enjoy-diving
* enjoy-diving-common
* enjoy-diving-web
* enjoy-diving-service

#### enjoy-diving
enjoy-diving 프로젝트의 `root project` (base gradle 설정을 포함)

#### enjoy-diving-common
enjoy-diving 프로젝트의 `common project`로 공통으로 사용하는 클래스를 정의

#### enjoy-diving-web
enjoy-diving 프로젝트의 `스쿠버 다이빙 로그 관리 project`로 웹 서버를 구현

##### dependencies info
* web, jpa, Security, validation, jdbc, devtools
* thymeleaf, jquery
* test, security test
* h2, mysql

##### package 구조



#### enjoy-diving-service
enjoy-diving 프로젝트의 `rest api project`로 연동에 필요한 API를 구현

* 인증 : `Spring Security Oauth2` 기반으로 구성하여 인증 하며, Token은 `redis`방식을 이용
* API : `Spring Web`기반에 `@RestController`를 이용

