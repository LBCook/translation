翻译基于 Docker v19.03

# Get started

## Docker overview

Docker is an open platform for developing, shipping , and running applications. 

Docker enables you to separate your applications from your infrastructure  so you can deliver software quickly. 

With Docker, you can manage your infrastructure in the same ways you manage your applications. 

By taking advantage  of Docker’s methodologies  for shipping, testing, and deploying code quickly, you can significantly reduce the delay between writing code and running it in production.



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



## The Docker platform

Docker provides the ability to package and run an application in a loosely isolated environment called a container. 

The isolation and security allow you to run many containers simultaneously on a given host. 

Containers are lightweight because they don’t need the extra load of a hypervisor, but run directly within the host machine’s kernel. 

This means you can run more containers on a given hardware combination  than if you were using virtual machines. 

You can even run Docker containers within host machines that are actually virtual machines!

Docker provides tooling and a platform to manage the lifecycle of your containers:

- Develop your application and its supporting components using containers.
- The container becomes the unit for distributing and testing your application.
- When you’re ready, deploy your application into your production environment, as a container or an orchestrated service. This works the same whether your production environment is a local data center, a cloud provider, or a hybrid of the two.

Docker通过提供宽松和隔离的容器环境，去打包和执行应用程序。

这个隔离性和安全性允许开发者同时在同一主机上执行很多的容器互不干扰。

之所以容器轻量级是因为不需要加载笨重的管理程序，而是直接运行在主机的内核上。

这意味着在相同的物理机器上可以执行的容器数量要比虚拟机多得多。

你甚至可以把docker运行在主机的虚拟机中。

docker提供工具和平台去管理容器的生命周期

- 使用容器部署你的应用程序和应用程序所需要的组件。
- 容器成为你发布和测试你的应用程序的最小单元。
- 当你准备使用容器或者编排服务去部署你的应用程序时，在本地的数据中心，或者是云服务，亦或者是两者都有的环境，其操作都是相同的，很容易部署的意思。



1. loosely 宽松
2. simultaneously 同时地
3. hypervisor 管理程序
4. combination 结合和组合
5. unit 单元
6. distributing 分散，发布
7. orchestrated精心安排
8. hybrid混合的，混合物



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

```
从图上可以看到，docker比较重要的组件

1. image 镜像
2. container 容器
3. network 网络
4. data volumes 数据卷

docker的构成

1. Server docker daemon 核心守护进程
2. REST API 用户与守护进程沟通
3. Client docker CLO 提供给我们开发者使用docker，是使用了REST API
```



The CLI uses the Docker REST API to control or interact  with the Docker daemon through scripting or direct CLI commands. Many other Docker applications use the underlying API and CLI.

The daemon creates and manages Docker *objects*, such as images, containers, networks, and volumes.



1. interact 相互作用
2. underlying adj. 潜在的；根本的；在下面的；优先的



命令行接口可以通过脚本或者命令行去控制docker守护进程，或者沟通。其他的docker应用使用CLI命令行或者底层API。

守护线程创建和管理docker对象，例如镜像，容器，网络，数据卷（所以这些东西叫做docker object）



## What can I use Docker for?

快速，一致的交付你的应用程序

**Fast, consistent delivery of your applications**

快速，一致的交付你的应用程序

Docker streamlines （n 流线 v 流线型，简化） the development lifecycle by allowing developers to work in standardized environments using local containers which provide your applications and services. 



Docker通过允许开发者使用本地容器让应用程序和服务运行在在相同标准的环境中从而简化了开发的生命周期。



Containers are great for continuous integration 集成 and continuous delivery 派送，交付 (CI/CD) workflows . 工作流



容器非常适合用于持续集成和持续交付的工作流



Consider the following example scenario 方案:

- Your developers write code locally and share their work with their colleagues 同事，同行  using Docker containers.
- They use Docker to push their applications into a test environment and execute automated and manual (adj体力的手动的，n说明书) tests.
- When developers find bugs, they can fix them in the development environment and redeploy them to the test environment for testing and validation 确认.
- When testing is complete, getting the fix to the customer is as simple as pushing the updated image to the production environment.

可以参考以下方案

- 你的开发者在本地编写代码然后通过容器分享给同事
- 他们使用docker推送他们的应用程序到测试环境，然后运行自动化和人工测试
- 当开发者发现bug的时候，确认并在开发环境解决他们，然后重新部署到测试环境
- 当一切搞定的时候可以很方便的提交镜像，然后部署到生产环境

这里面涉及三个环境，并且都是相同的，docker为你屏蔽了环境问题，轻松交付

1. development environment 开发环境
2. test environment 测试环境
3. production environment 开发环境



**Responsive deployment and scaling**

响应式开发和扩展

Docker’s container-based platform allows for highly portable（adj 手提的，便携的 n 手提打印机） workloads. 

docker 容器的执行平台可以被高度移植

Docker containers can run on a developer’s local laptop, on physical or virtual machines in a data center, on cloud providers, or in a mixture 混合物 of environments.

docker容器可以运行在开发者的本地手提，或者在物理机，虚拟机上，云服务器上或者混合环境中。

Docker’s portability and lightweight nature also make it easy to dynamically manage workloads, scaling up 放大 or tearing down 减少 applications and services as business needs dictate 命令, in near real time. 几乎是实时的

Docker的可移植性和轻量级的特性让它可以在执行环境中动态管理。

在真实环境下根据不同的场合增加或者减少对应应用程序和服务的数量。

scaling up 按比例放大

tearing down 减少