---
title: Interaction-Oriented Service EntityPlacement in Edge Computing Placement in Edge Computing
date: 2022-02-12 21:46 +0800
author:
  name: Sophia-whale
  link: https://github.com/sophia-whale
categories: [Report, Edge Computing]
tags: [interaction-oriented, edge computing]
math: true
mermaid: true
---
# Interaction-Oriented Service Entity Placement in Edge Computing

边缘计算中面向交互的实体放置

## Abstract

分布式交互应用通常需要快速处理大量数据和及时的延迟敏感的操作数据和元数据的交换。这一需求使得传统的基于移动端的或者基于云端的方式不再高效适用。边缘计算的出现，DIA可以从边缘基础设施中租借资源来放置服务实体，这些服务用于存储用户数据以及执行计算敏感的任务。一个基础的问题在于在总安置成本不超过指定的预算门槛的约束条件下，如何放置服务实体才能实现DIA用户间的低延时配对交互。在本文中，我们对服务实体放置问题进行了形式化建模，并且借助对集合覆盖问题的多项式还原证明了这是一个NP完全问题。

In this article, we formally model the service entity placement problem and prove that it is NP-complete by a polynomial reduction from the set cover problem. We present GPA, an efficient algorithm for service entity
placement, and theoretically analyze its performance. We evaluated GPA with both real-world data trace-driven simulations, and observed
that GPA performs close to the optimal algorithm and generally outperforms the baseline algorithm. We also output a curve showing the
trade-off between the weighted average interaction delay and the budget threshold, so that a DSP can choose the right balance.
Index Terms—Edge computing, distributed interactive applications, interaction delay, service entity placement

> set cover problem

> NP-complete
