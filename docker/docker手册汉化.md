Docker overview

Docker is an open platform for developing, shipping 运送, and running applications. 

Docker enables you to separate分开 your applications from your infrastructure 基础设施 so you can deliver software quickly. 

With Docker, you can manage your infrastructure in the same ways you manage your applications. 

By taking advantage 优势 of Docker’s methodologies 方法论 for shipping, testing, and deploying部署 code quickly, you can significantly 显著的 reduce the delay between writing code and running it in production.



Docker 概述

Docker 是一个为了开发，移植，和执行程序开放的平台。

Docker 可以让你的程序和基础环境分开，这样你可以快速的交付软件。

在Docker你可以管理你的基础环境就像你管理你的代码。

根据Dokcer的移植，测试和快速部署代码，你可以明显的减少在写代码和程序完全部署之间的延迟。



1. Shipping 运送，船只运送；ship船
2. separate 分开
3. Infrastructure 基础设施，这里应该指的是程序运行的环境
4. Advantage 优势
5. methodologies 方法论
6. deploying 部署
7. significantly 显著的



------

## The Docker platform

Docker provides the ability to package and run an application in a loosely宽松 isolated environment called a container. 

Docker通过提供宽松和隔离的容器环境，去打包和执行应用程序。

The isolation and security allow you to run many containers simultaneously同时地 on a given host. 

这个隔离性和安全性允许开发者同时在同一主机上执行很多的容器互不干扰。

Containers are lightweight because they don’t need the extra load of a hypervisor管理程序, but run directly within the host machine’s kernel. 

之所以容器轻量级是因为不需要加载笨重的管理程序，而是直接运行在主机的内核上。

This means you can run more containers on a given hardware combination 结合和组合 than if you were using virtual machines. 

这意味着在相同的物理机器上可以执行的容器数量要比虚拟机多得多。

You can even run Docker containers within host machines that are actually virtual machines!

你甚至可以把docker运行在主机的虚拟机中。

Docker provides tooling and a platform to manage the lifecycle of your containers:

- Develop your application and its supporting components using containers.
- The container becomes the unit 单元 for distributing 分散，发布 and testing your application.
- When you’re ready, deploy your application into your production environment, as a container or an orchestrated精心安排 service. This works the same whether your production environment is a local data center, a cloud provider, or a hybrid混合的，混合物 of the two.

docker提供工具和平台去管理容器的生命周期

- 使用容器部署你的应用程序和应用程序所需要的组件。
- 容器成为你发布和测试你的应用程序的最小单元。
- 当你准备使用容器或者编排服务去部署你的应用程序时，在本地的数据中心，或者是云服务，亦或者是两者都有的环境，其操作都是相同的，很容易部署的意思。

## Docker Engine

*Docker Engine* is a client-server application with these major components:

- A server which is a type of long-running program called a daemon process (the `dockerd` command).
- A REST API which specifies （指定） interfaces that programs can use to talk to the daemon and instruct （指导，通知） it what to do.
- A command line interface (CLI) client (the `docker` command).

Docker引擎是一个一个C-S应用程序，主要包括以下部分

- 一个服务器，一个常驻应用，名字叫守护进程（dockerd命令）
- 一套RESTful风格的API，用于和守护进程交互，和命令什么需要做（有可能在集群中使用）
- 一套命令行接口就是我们交互的docker命令（docker）

![image-20200606224302797](/Users/linbin/Library/Application Support/typora-user-images/image-20200606224302797.png)

从图上可以看到，docker比较重要的管理

1. image 镜像
2. container 容器
3. network 网络
4. data volumes 数据卷

docker的构成

1. Server docker daemon 核心守护进程
2. REST API 用户与守护进程沟通
3. Client docker CLO 提供给我们开发者使用docker，是使用了REST API



The CLI uses the Docker REST API to control or interact 相互作用 with the Docker daemon through scripting or direct CLI commands. Many other Docker applications use the underlying API and CLI.

命令行接口可以通过脚本或者命令行去控制docker守护进程，或者沟通。其他的docker应用使用CLI命令行或者底层API。

The daemon creates and manages Docker *objects*, such as images, containers, networks, and volumes.

守护线程创建和管理docker对象，例如镜像，容器，网络，数据卷