---
layout: post
title: Chapter 1 Operating System Overview
date: 2022-03-08 11:14 +0800
author:
  name: Sophia-whale
  link: https://github.com/sophia-whale
description:
categories: [Operating System, Chapter 1 Operating System Overview]
tags: [operating system, interrupt, system call]
math: true
mermaid: true
---
## 基本概念

### 1.1 操作系统

* 操作系统是计算机系统最底层的软件，管理者计算机的各种资源。向下管理着计算机的硬件资源，向上为应用程序提供运行环境，并为用户提供良好的交互界面。此外还是资源的分配器以及程序运行的管理程序。
* 程序运行环境
  * 内核态（管态）：执行特权和非特权指令
  * 用户态（目态）：执行非特权指令
  * 中断和异常
  * 系统调用
* 原语：由若干个机器指令组成的完成某一特定功能的一段程序，具有不可分割的原子性，即在执行的过程中不允许中断。

### 1.2 并发和共享

* 并发指宏观上多道程序在同时执行，通过分时实现若干进程在同一时间段内执行。
* 并行指微观上多道程序同时执行，需要硬件支持若干进程在同一时刻同时执行。
* 共享指系统中的资源可供内存中的多个并发执行的进程共同使用。
* 并发和共享的关系
  * 资源共享是以并发为前提的，没有多程序的并发执行，也就无需资源共享。
  * 并发执行以合理资源共享管理为基础，若不能合理调度资源，多程序并发执行将会十分混乱。

## 操作系统的发展

### 2.1 手工和单道批处理

* 手工：人工操作程序运行的全过程，装入、运行、结果输出等。
* 单道批处理：系统对作业成批进行处理，但内存中始终保持一道作业。作业按照装入顺序自动逐个运行。当程序完成或发生异常时，才将后续程序换入内存。

### 2.2 多道批处理

* 系统对作业成批进行处理，多个程序进入内存并在CPU中交替运行，共享系统中的各种资源。实现宏观上并行，微观上串行。
* 当程序因I/O请求而暂停运行时，CPU会立刻转去运行另一道程序。
* 在多道批处理时，需合理处理一下问题
  * 如何分配CPU
  * 如何分配内存
  * 如何分配I/O设备
  * 如何管理程序和数据

### 2.3 分时

* 多个用户通过终端共享一台主机。
* 系统把CPU的运行时间分成很短的时间片，轮流分给各用户使用。
* 用户通过终端交互直接控制程序运行，因此系统中的每个用户可独立操作并在很短的时间内获得响应。

### 2.4 实时

* 计算机系统在接受到外部信号后及时进行处理，并在严格的时限内完成事件。
* 实时系统分为两种
  * 硬实时系统指某个任务必须在某个时间发生。
  * 软实时系统指能够接受偶尔的违反时间规定不会造成永久性伤害。

### 2.5 网络和分布式

* 网络指把计算机网络中的各台计算机有机地结合起来，实现计算机之间的数据通信。
* 分布式
  * 系统中的任意两台计算机通过通信交换信息。
  * 每台计算机具有同等的地位。
  * 每台计算机上的资源为所有用户共享。
  * 工作可有分布式结构上的多个用户协同完成。
  * 可形成子系统可重构。

## 操作系统结构

* 单体式
* 层次式
* 虚拟机
* 微内核：有效的分离了内核和服务、服务与服务，使得接口更清晰，维护代价降低，提升了操作系统的可靠性。但频繁在用户态和内核态切换会增大系统执行开销。
* 客户/服务器

## 中断和异常

### 4.1 基本概念

* 中断：也称外中断，指来自CPU执行指令以外的事件的发生。分为外设请求和人为干预两类
* 异常：也称为内中断、例外或陷入，指源自CPU执行指令内部的事件。分为指令中断和强迫中断（硬件故障和软件中断）。

### 4.2 中断源

* 外中断
  * 外部设备请求中断：外部设备在完成自身操作后向CPU发出中断请求。
  * 实时时钟请求中断：CPU发出命令使时钟开始工作，当达到规定时间时，时钟电路发出中断请求，CPU转去完成监测和控制工作。
  * 数据通道中断（DMA中断）：CPU收到中断后停止工作，直接与存储器交换数据时发出的请求中断。
* 内中断
  * 程序自愿中断：CPU执行了trap指令；用户调试程序，中断检查寻找程序错误。
  * 故障强迫中断：故障检测到运算溢出、外部设备故障等报警信号。

### 4.3 特权指令

具有特殊权限的指令，仅在内核态使用，用户通过系统调用使用该指令。

![img-description](/assets/posts/20220308/4.3.png)
*指令周期*

### 4.4 中断流程

psw寄存器：程序状态寄存器

![img-description](/assets/posts/20220308/4.4.png)
*中断流程图*

## 系统调用

5.1 实现过程

* 提供用户程序和操作系统之间的接口，以便用户调用特权指令。
* 系统调用是系统的保护机制，防止应用程序直接调用操作系统，从而保证系统安全。

![img-description](/assets/posts/20220308/5.1.png)
系统调用实现过程

5.2 运行环境切换

陷入机制指的是程序进行系统调用时系统所要执行的状态。

![img-description](/assets/posts/20220308/5.2.png)
*陷入机制切换*
