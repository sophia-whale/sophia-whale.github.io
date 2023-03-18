---
layout: post
title: Docker basics
date: 2023-03-18 19:47 +0800
author:
  name: Sophia-whale
  link: https://github.com/sophia-whale
description: Notes for Docker.
categories: [Docker, basics]
tags: [docker, basics]
math: true
mermaid: true
---
## Docker概述

为跨平台的开发部署环境带来了便利。轻量 隔离 跨平台

### 1.0 Docker背景

虚拟机缺点

- 启动慢
- 资源占用多

比较Docker和虚拟机技术的不同：

- 传统虚拟机，虚拟出一条硬件，运行一个完整的操作系统，然后在这个系统上安装和运行软件
- 容器内的应用直接运行在宿主机的内容，容器是没有自己的内核的，也没有虚拟我们的硬件，所以就轻便了
- 每个容器间是互相隔离，每个容器内都有一个属于自己的文件系统，互不影响

DevOps

- 应用可以更快速的交付和部署
- 更易扩容升级
- 更易运维
- 更高效地利用系统资源

### 1.1 Docker运行流程

- docker开始运行
- 在本机寻找镜像
- 若镜像存在，则使用镜像运行；若不存在，则在远程仓库中下载镜像
- 若镜像在远程仓库中存在，则将镜像下载到本地；若不存在，则返回错误，找不到该镜像

![img-description](/assets/posts/20230318/1.1.png)

**镜像（Image）：**作为应用环境模板，通过某一个镜像可以创建多个容器。

**容器（container）：**Docker通过容器技术，独立运行一个或一组应用，通过镜像来创建

**容器（repository）：**存放镜像的仓库

### 1.2 Docker底层原理

Docker是一个CS结构的系统，Docker的守护进程运行在主机上，docker的守护进程运行在主机上，通过Socket从客户端访问！Docker Server接收到Docker-Client的指令，就会执行这个指令！

![img-description](/assets/posts/20230318/1.2.png)

## Docker常用命令

### 2.1 帮助命令

> docker version
>
> docker info
>
> docker 命令 --help # 帮助命令

### 2.2 镜像命令

> docker images
>
> > -a # 所有镜像
> >
> > -q # 只显示镜像的id
> >
> > -f # 镜像的过滤器
>
> docker search
>
> > -f, --filter=STARS=3000
>
> docker pull 镜像名[:tag]
>
> > tag # 指定镜像版本
>
> docker rmi
>
> > -f # 强制删除
> >
> > -f 镜像id # 可用空格分隔删除多个镜像
> >
> > -f ￥(docker iamges -aq) # 删除全部的镜像

### 2.3 容器命令

> docker pull centos
>
> docker run 参数 image
>
> > --name="Name" # 容器名称（用于区分容器）
> >
> > -d # 后台方式运行
> >
> > -it # 使用交互方式运行，进入容器 
> >
> > > exit退出容器(并退出)；Ctrl+P+Q退出容器且不停止
> >
> > -p 主机端口：容器端口
>
> docker ps
>
> > -a # 当前正在运行的容器以及历史运行
> >
> > -n=? # 显示最近创建的容器
> >
> > -q # 只显示容器的编号
>
> docker rm 容器id
>
> docker start 容器id
>
> docker restart 容器id
>
> docker stop 容器id
>
> docker kill 容器id

### 2.4 常用其他命令

> docker run -d 镜像名
>
> > docker容器使用后台运行时，必须要有一个前台进程 -d可显示后台运行容器的id
> >
> > docker在启动后发现自身并未提供服务，就会自动关闭
> >
> > 例如nginx作为后台进程，就会被docker认为未提供服务，就会立刻停止进程
>
> docker run -it 镜像名
>
> docker logs 选项 容器id
>
> > -tf 显示日志信息（实时更新）
> >
> > --tail n 查看最后n行日志信息
>
> docker inspect 容器id 查看容器的状态信息
>
> docker exec -it 容器id bashshell 进入当前容器后开启一个新的终端进程
>
> docker attach 容器id 进入容器正在执行的终端进程
>
> docker cp 容器id:容器路径 主机目的路径 
>
> docker

- 外网：即是linux外部的网络
- 阿里云的安全组：阿里云的端口要从这里开放，比如开放了3344。
- 防火墙3344：是linux内部的防火墙开启了3344端口
- -p 3344：80：通过这个操作，暴露端口，我们宿主机的3344就能访问到容器的80端口

![img-description](/assets/posts/20230318/2.4.png)



## 容器数据卷

### 3.1 概念

容器的持久化和同步操作，使得容器间可以数据共享
