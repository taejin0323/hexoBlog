---
title: CDA 란?
categories:
  - IHIS
  - HL7
tags:
  - hl7
  - cda
date: 2019-01-19 19:07:59
subtitle: 19.01.17 내용 복습
cover: https://images.slideplayer.com/25/7958574/slides/slide_1.jpg
---

----------
<blockQuote>*본 문서는 IHIS 연구소의 **'HL7 Clinical Document Architecture Release 2'** pdf 문서를 기반으로 작성 되었습니다.* </blockQuote>

----------
# CDA 개요
## 1.  CDA의 정의(Definition)

정식 명칭은 <span style="color:blue">The HL7 **Clinical Document Architecture (CDA)**</span>로
 **"공유 목적으로 하는 *임상 문서(clinical document)*의 구조와 의미를 명시하는 문서 표기(Markup)의 표준"**이라고 정의 되어있다.


 <div style="font-size:small">*임상문서는 의사가 환자를 진료 후 진단된 병명 및 진료내역 등을 기술하고 투약, 주요 실시검사 내용 등 주요 진료결과를 포함하는 문서이다.
    <div style="border:1px solid; padding:10px; box-sizing: border-box;">++임상 문서(Clinical document)++는 ==다음과 같은 특성==을 가진다 :
    - **Persistence (존속성)**
    &emsp;- 문서는 지역 및 규제 요건에 의해 정의된 기간 동안 변경되지 않은 상태로 계속 존재한다.
    - **Stewardship (관리 책임)**
    &emsp;- 문서는  그 관리를 위임받은 기관에 의해 보존된다.
    - **Potential for authentication (인증가능성)**
    &emsp;- 문서는 합법적으로 인증받고자 하는 정보의 집합물이다.
    - **Context (문맥))**
    &emsp;- 임상 문서에 대한 기본 맥락(default context)를 설정한다.
    - **Wholeness (전체성)**
    &emsp;- 문서의 인증은 전체적으로 적용되며 문서 전체 맥락(context)이 없는 부분에는 적용되지 않는다.
    - **Human readability (가독성)***
    &emsp;- 사람이 읽을 수 있어야 한다.
        </div>
 </div>

## 2. CDA의 주요 특성(Key aspects)

- <span style="color:green;">Extensible Markup Language**(XML)**</span>로 인코딩 된다.

- <span style="color:green;">HL7 Reference Information Model(이하 RIM)</span>로부터 기계처리적 의미가 유도되고 <span style="color:green;">HL7의 버전 3 데이터 타입</span>을 사용한다

- 표현력이 풍부하고 유연하다.
	-<span style="color:green;">document 레벨, section 레벨, entry 레벨의 템플릿</span>은 일반적인 CDA 명세를 통제하기 위해 사용될 수 있다
