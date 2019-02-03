---
title: 스프링 프레임워크 핵심 개념
author:
  nick: TAEJIN
  link: null
categories:
  - WEB
  - SPRING
tags:
  - SPRING
date: 2019-02-02 15:16:10
subtitle: 스프링 프레임워크의 핵심 기술
cover: https://spring.io/img/spring-by-pivotal.png


---

### Reference

[Spring의 시작, 프레임워크의 구성요소와 동작원리](https://asfirstalways.tistory.com/334)

**POJO**
[스프링 프레임워크 1 - POJO에 대하여](https://limmmee.tistory.com/8)
[Understanding : POJO](https://spring.io/understanding/POJO)

**IoC/DI**



------

:book: **목차** :book:

- [POJO](#pojo)
- [IoC / DI](#ioc-/-di)
- [AOP](#aop)
- [PSA](#psa)



## 핵심 개념들

- 스프링 프레임워크를 공부하면서 자주 언급되고 매우 중요하다고 생각하는 용어들을 정리했습니다
- 아직 많은 것을 알지 못하기 때문에 자세하고 정확한 내용은 제가 참조한 사이트나 따로 검색 또는 책을 통해 알아보는 것을 권장드립니다.



### POJO

:heavy_check_mark: **Plain Old Java Object** : (직역) 평범한 옛날 자바 객체



스프링 공식 홈페이지에서는 POJO를 다음과 같이 소개합니다.

> By using plain old Java objects, your code is much more simplified, which lends to better testing, flexibility, and ability to change technical decisions at future stages based on knowledge and shifting requirements.

POJO를 사용함으로써,

- 코드가 간결해져서 테스트하기 편해지고 (비즈니스 로직과 특정 환결/로우 레벨 종속적인 코드를 분리함)
  쉽게 말해 인터페이스, 상속이 없는 것
- 유연해서 객체지향적 설계의 자유료운 사용이 가능



**POJO 기반의 프레임워크 == 스프링 프레임워크**

많은 POJO 프레임워크가 있고 하이버네이트와 스프링이 대표적이라고 할 수 있습니다. (이 둘의 차이점은 굳이 자세히 알아보지는 않겠습니다.) 스프링 프레임워크가 그 많은 POJO 프레임워크 제품 중 하나라는 것만 알고 넘어가시면 될 것 같습니다.



**진정한 POJO 프로그래밍**

<u>자바의 객체지향적인 특징</u> 을 살려 비즈니스 로직에 충실한 개발이 가능하도록 하는 것이 진정한 POJO 프로그래밍이라고 할 수 있습니다. 마치 자바를 처음 배울 때 흔히 하는 실수로, 개발은 자바로 하지만 실제로는 C 언어를 배우며 익숙해진 절차지향 방식으로 구현하는 것을 생각하시면 되겠습니다. POJO 프레임워크 제품을 사용한다고 해서 자동으로 POJO 형식의 개발을 하고 있다고 할 수 없습니다.



스프링 프레임워크를 사용하면 **POJO로 애플리케이션을 만들고 엔터프라이즈 서비스를 비침투적으로 POJO에 적용할 수 있다** 정도로 이해하고 넘어가시면 될 것 같습니다.



### IoC / DI





### AOP



### PSA

<br><br><br>
