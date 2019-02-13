---
title: 운영체제 - Overview_2
author:
  nick: TAEJIN
  link: null
categories:
  - OS
tags:
  - OS
  - 운영체
date: 2019-02-12 18:51:53
subtitle: 컴퓨터 시스템 구조
cover: https://safebytes.com/wp-content/uploads/2016/10/OperatingSystem-min.jpg

---

:book: **목차** :book:

1. [컴퓨터 시스템 구조](#컴퓨터-시스템-구조)
   2.1 [컴퓨터 시스템의 동작](#21-컴퓨터-시스템의-동작)
   2.2 [I/O 구조](#22-io-구조)
   2.3 [저장 구조](#23-저장-구조)

------

# 컴퓨터 시스템 구조

## 2.1 컴퓨터 시스템의 동작

<img style="height:450px; align:center;" src="https://i.imgur.com/8JAIHTg.png">

- 컴퓨터는 <u>공유된 주기억장치에 접근을 제공하는 공통 버스에 의해 연결된 CPU와 여러 개의 장치 제어기(Device controller)로 구성</u>되어 있습니다.

  - 장치 제어기(Device Controller)
    각 장치(디스크, 오디오 장치, 비디오 디스플레이)를 관리
  - 장치 제어기와 CPU는 병행으로 수행되므로 이들은 주기억장치 접근에 대해 경쟁합니다. 주기억장치 제어기(Memory Controller)는 이들의 접근을 동기화해줍니다.

- 컴퓨터가 처음 구동되면 초기에 실행될 프로그램이 필요합니다. 이 프로그램을 **부트스트랩 프로그램(Bootstrap program)** 이라고 합니다. 이 프로그램은 보통 컴퓨터 하드웨어 내에 ROM(Read-Only-Memory)에 저장되어 있습니다.

  - 부트스트랩 프로그램(Bootstrap program)
    모든 하드웨어를 초기화하고 운영체제 커널을 주기억장치에 적재한 후에 커널을 실행


<br>
- 컴퓨터에서 사건(Event)의 발생은 **인트럽트(interrupt)** 신호, **트랩(trap)** 혹은 **예외(Exception)** 를 통해 운영체제에 통보됩니다. 사건이 발생되면 CPU는 현재 수행중인 작업을 멈추고, 운영체제 내에 있는 특정 코드를 실행합니다. 이 실행이 끝나면 다시 멈춘 작업을 재개합니다.

<img height="250px" src="http://pediaa.com/wp-content/uploads/2018/08/Difference-Between-Trap-and-Interrupt_Figure-1.png">

<span style="color:red">Interrupt</span>

- **Hardware Interrupt** : 하드웨어는 CPU에 특정 신호를 보내어 인트럽트의 발생을 알림
  -- 예) 키보드 입력, I/O interrupt, timer ticks
- 하드웨어가 시스템의 수행 흐름을 바꾸기 위해 발생하는 것
- 비동기식(Asynchronus Interrupt)



<span style="color:red">Trap</span>

- **Software Interrupt** : 시스템호출(System call)이라는 특정 연산을 실행하여 일부로 발생시키거나 오류 때문에 자발적으로 발생
  -- 오류의 예) 0 나누기, 부적합한 주기억장치 접근(page fault)
- 동기식(Synchronus Interrupt)



<span style="color:red">Exception</span>

- 프로세서에 의해 자동으로 처리
- **Faults** 와 **Aborts** 로 세분화 가능
  -- Faults : 복구 가능한 오류 (recoverable error)
  -- Aborts : 처리하기 어려운 오류 (an error that is difficult to handle)


<br>
## 2.2 I/O 구조

- 장치 제어기(Device controller)에 따라 하나 이상의 장치가 제이거에 연결될 수 있습니다
- 장치 제어기는 지역 버퍼와 몇 개의 특수 목적 레지스터를 유지합니다
- 장치 제어기는 연결된 주변장치와 지역 버퍼 간에 데이터 이동을 책임집니다. 이 버퍼의 크기는 주변장치에 따라 다릅니다.



### 2.2.1 I/O Interrupt

- 입출력의 두 가지 형태
  -- 동기식 입출력(Synchronous I/O) : 입출력이 시작되면 요청한 프로세서는 입출력이 완료될 때까지 기다림
  -- 비동기식 입출력(Asynchronous I/O) : 요청한 프로세서는 입출력이 완료될 때까지 기다리지 않고 계속 다른 작업을 수행
- 입출력의 완료를 기다리는 방법
  -- 특수한 명령어 사용
  -- 대기 루프 사용
- <u>만약 CPU가 입출력 완료를 항상 기다리면</u> 한번에 한 입출력만 가능
  하지만 시스템의 효율을 높이기 위해 입출력과 계산을 병행할 수 있어야함으로 이 방법은 비효율적
- 운영체제는 여러 개의 입출력 요청을 관리하기 위해 **장치 상태 테이블(device-status table)** 을 유지합니다. 각 장치마다 대기큐를 유지합니다.

<img height="350px" src="https://www.cs.uic.edu/~jbell/CourseNotes/OperatingSystems/images/Chapter13/13_09_DeviceStatusTable.jpg">



### 2.2.2 DMA 구조

- 속도가 느린 입출력 장치는 하나의 입력을 받은 후에 다음 입력까지 CPU는 다른 유용한 작업을 할 수 있습니다.
  반대로 속도가 빠른 입출력 장치는 인트럽트가 너무 빈번하게 발생하여 CPU가 다른 유용한 작업을 할 시간이 없습니다.
- 이것을 해결하기 위해 사용하는 기법이 **DMA(Direct Memory Access)** 입니다.
- DMA 방식에서 장치 제어기는 데이터 블록을 CPU의 관여없이 직접 주기억장치로 이동하며, 인터럽트는 바이트 단위가 아닌 블록 단위로 발생합니다.

<img style="align:center;" src="http://pds17.egloos.com/pds/200910/26/90/c0098890_4ae5a423a7cef.jpg">


<br>
## 2.3 저장 구조







## Reference

[Difference between Trap and Interrupt](http://pediaa.com/difference-between-trap-and-interrupt/)

[DMA-CPU몰래 영차영차](http://recipes.egloos.com/5152867)



<br><br><br>
