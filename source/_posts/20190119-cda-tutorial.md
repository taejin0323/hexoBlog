---
title: CDA 란?
subtitle: 19.01.17 내용 복습
categories:
  - null
tags:
  - null
cover: 'https://images.slideplayer.com/25/7958574/slides/slide_1.jpg'
date: 2019-01-19 19:07:59
---

### Related Posts


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


## 3. CDA의 목표
* 환자의 보호에 우선권을 둔다.
* 가능한 광범위한 시스템에서 사용이 가능하도록 하면서 비용이 효율적이게 구현한다.
* 전문 지식의 수준이 다른 사용자들도 판독이 가능하도록 지원한다.
* 인코딩된 정보가 오래 유지되도록 한다.
* 합리적이고 빠르게 디자인이 되도록 한다.

## 4. CDA Document의 주요 요소들
<center> ![CDA document](/img/componentsOfCDA.png) </center>


* **The Header**
- &lt;ClinicalDocument&gt; 태그와 &lt;structuredBody&gt; 태그 사이에 있다
- 문서를 확인하고 분류하며 ==인증, 진료, 환자, 관련된 제공자들의 정보==를 담는다.

* **The Body**
- 진료 보고서(clinical report)를 담고 있다.
- 1)비정형화(unstructured blob)
  2)정형화된 표기(structured markup) 둘 중 하나이다.
  - 위 예제는 &lt;structuredBody&gt; 태그로 정형화된 구조이고, document section이 되풀이해서 올 수 있는 recursive 구조이다.
