---
layout: post
title: Chapter 1 Introduction to Database
date: 2022-02-26 10:58 +0800
author:
  name: Sophia-whale
  link: https://github.com/sophia-whale
description: Notes from Database Principles, Programming and Performance.
categories: [Database, Chapter 1 Introduction to Database]
tags: [datebase, database conception]
math: true
mermaid: true
---
### 1.1 数据库的基本概念

数据库管理系统（DBMS）：数据库管理系统是一种软件产品，它把一个企业的数据以记录的形式在计算机中保存起来。

### 1.2 数据库用户

* 最终用户——交互式用户。
  * 临时用户一-用SQL访问DBMS的用户。
  * 初级用户——通过菜单访问DBMS的用户。·
* 应用程序员——编写菜单程序的程序员。
* 数据库管理员—-管理DBMS的专家。

### 1.3 关系数据库

1. 关系模型
   遵循第一范式，通过关系代数基于表进行操作。
2. 基本SQL语言
   增删改查
3. 对象——关系模型
   表格内容可以为封装后的复杂类型，增删改查时将复杂类型的数据当作一个整体处理

   ![img-description](/assets/posts/20220226/object-database-example.png)
   _object-database-example_

   ![img-description](/assets/posts/20220226/ORSQL.png)
   *ORSQL语句*
4. 访问数据库的程序

   程序根据用户的请求进行SQL查询，但由于C、Java等高级语言不支持SQL查询，故需增加特殊的标记（如C开头的exec sql）。诸如此类的嵌入式编程使得程序和数据库能够相互独立，程序逻辑不必了解数据库的访问设置、数据的存储结构以及存取方法等细节。
5. 数据库设计*

   * E-R模型：实体（Entity）是一类真实存在、彼此之间可区分的对象；关系（Relation）表示实体之间的联系。

     ![img-description](https://file+.vscode-resource.vscode-webview.net/assets/posts/20220226/object-database-example.png)

     _E-R example_
   * 数据库规范化
6. 完整性约束、安全、视图*

   * 完整性约束：对数据增加约束条件，在数据库中形成数据防护，而不用等到程序运行时再进行判断，从而进一步防止SQL注入侵害数据。
   * 安全性约束：对用户的增删改查权限进行约束，使用Grant对用户进行授权。
   * 数据库视图：创建一个虚拟的视图表，用于存储常用的SQL查询语句，从而简化数据库的逻辑结构，加强了程序——数据独立的概念。应用程序逻辑不仅不受物理存储结构的变化的影响，也不受基本表结构的逻辑变化的影响，但目前视图仍受到很多限制(例Update，Insert和Delete语句)。
7. 索引*

   * 数据库的物理设计：设计如何在磁盘上安排基本表，以及创建什么样的索引来优化应用程序和交互操作所请求数据的访问。
   * 属性充当索引：逐行查找对比
   * 次序索引：把行按照某种索引的次序排列，称为聚簇。
8. 查询处理——查询优化
9. 更新事务*

   * 数据库事务：事务把―系列对记录的读和更新操作组成一个不可分割的包。事务具有原子性，这意味着事务所涉及的行只能在事务执行前或事务结束后才能被其他操作访问。在事务执行过程中，决不允许有其他操作访问相关的行。
   * 并发访问冲突处理（两段锁方案）：对被某个事务访问的记录加锁，以防止这个记录被其他并发用户访问，-般在这个事务完成时才对记录解锁。
10. 并行和分布式数据库
