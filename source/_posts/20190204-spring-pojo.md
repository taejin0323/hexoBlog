---
title: 스프링 - POJO
author:
  nick: TAEJIN
  link: null
categories:
  - WEB
  - SPRING
tags:
  - SPRING
  - POJO
date: 2019-02-04 00:59:18
subtitle: POJO에 대해서 알아보자
cover: https://spring.io/img/spring-by-pivotal.png
---

### Reference
[Plain Old Java Object-위키](https://ko.wikipedia.org/wiki/Plain_Old_Java_Object)
[POJO(Plain Old Java Object)](https://itewbm.tistory.com/entry/POJOPlain-Old-Java-Object)

------

​	:book: **목차** :book:

- [POJO](#POJO)



` 아직 많은 것을 알지 못하기 때문에 자세하고 정확한 내용은 제가 참조한 사이트나 따로 검색 또는 책을 통해 알아보는 것을 권장드립니다.`


#### POJO

:heavy_check_mark: **Plain Old Java Object** : (직역) 평범한 옛날 자바 객체

 처음에 단순히 정의를 검색하다보니 정말 단순한 자바 객체인 것 같은데 왜 굳이 POJO라는 단어를 사용하는지 혼란스러웠습니다. Stack Overflow 같은데서도 자바빈과 비교하는 토론이 있기도하고 솔직히 현재도 완전히 이해했다고는 할 수 없지만 제가 생각하는 내용을 적었습니다.



​	***POJO의 탄생***

> Any fool can write code that a computer an understand. Good programmers write code that humans can understand.
> 컴퓨터가 이해하는 코드는 어느 바보나 짤 수 있다. 좋은 프로그래머는 사람이 이해하는 코드를 짠다.
> > Martin Fowler, <<리팩토링>>

 POJO는 리팩토링과 애자일 소프트웨어 개발로 유명한 영국의 소프트웨어 개발자 **마틴 파울러** 가 2000년 가을에 열렸던 어느 컨퍼런스의 발표를 준비하면서 처음 사용한 단어입니다. 그는 당시 <u>EJB(Enterprise JavaBean) 보다는 단순한 자바 오브젝트에 도메인 로직을 넣어 사용하는 것이 여러가지 장점이 있는데 왜 사람들이 EJB가 아닌 '평범한 자바 오브젝트'를 사용하기를 꺼려하하는지에 대해 의문을 가졌습니다</u> 그래서 그의 생각을 널리 알리기 위해 그는 개발자들의 심리를 이용한 기발한 전략을 세웠습니다. POJO라는 용어를 만들고 이를 기반으로한 기술을 사용한다고 발표하여 다른 개발자들에게 마치 새로운 첨단 기술인 듯한 인상을 주었습니다.
 정리하자면, 마틴 파울러는

- 자바 개발자들에게 **단순하고 평범한 자바 오브젝트 사용을 권장** 하고
- **자신의 생각을 효과적으로 전달** 하기 위해 POJO라는 단어를 사용 했습니다
  Cf) 이를 계기로 다른 분야에서도 비슷한 용어들이 생긴 것을 보면 그의 전략이 성공적이 였다는 것을 쉽게 알 수 있습니다.
  - Plain Old Data Structures(PODS) - C++ 언어에서 오직 C 언어의 특징만 사용하는 경우
  - Plain Old Documentation(POD) - 펄(Perl) 언어에서 사용
  - Plain Old PHP Object(POPO) - PHP 언어에서 사용



이제 겨우 POJO의 형체가 희미하게 보이는 것 같습니다. 이 친구를 더 자세히 알기 위해선,
- EJB(Enterprise JavaBean)는 무엇이며 어떤 문제점이 있는가
- POJO란 그럼 그저 EJB 이전의 방식으로 돌아가는 것인가
를 알아야 겠다고 생각했습니다.



​	***Enterprise JavaBean?***



<br><br><br>
