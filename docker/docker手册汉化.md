翻译基于 Docker v19.03

https://docs.docker.com/get-started/overview/

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



**Hypervisor**，又称**虚拟机监视器**（英语：virtual machine monitor，缩写为 VMM），是用来建立与执行[虚拟机器](https://baike.baidu.com/item/虚拟机器)的软件、固件或硬件。



**Running more workloads 负载 on the same hardware**

相同的硬件下可以运行更多的负载

Docker is lightweight and fast. 

Docker 轻量级且快

It provides a viable 可行的, cost-effective 费用+效率=划算 alternative 二选一  to hypervisor-based virtual machines, so you can use more of your compute capacity to achieve your business goals. 

对比虚拟机容器技术提供了更加划算和可行的方案，可以使你在为了实现业务目标中使用到更多的计算机能力。

Docker is perfect for high density 密度 environments and for small and medium deployments where you need to do more with fewer resources.

Docker非常适合高密度的环境 和 哪些资源有限的小或者中形开发者，节约很多资源的意思。



## Docker architecture 架构

Docker uses a client-server architecture. The Docker *client* talks to the Docker *daemon*, which does the heavy lifting 举起，承载 of building, running, and distributing your Docker containers. The Docker client and daemon *can* run on the same system, or you can connect a Docker client to a remote Docker daemon. The Docker client and daemon communicate using a REST API, over UNIX sockets or a network interface.

Docker 使用CS架构。Docker客户端与Docker守护进程交流，Docker守护进程主要处理镜像的构建，容器的运行和销毁。Docker客户端和Docker守护进程可以运行在相同的系统上，或者也可以通过远程连接。他们之间的交流建立在UNIX socket 或者 网络接口 上，使用的是REST API（一种规范）



<img src="/Users/linbin/Library/Application Support/typora-user-images/image-20200610220350611.png" alt="image-20200610220350611" style="zoom:40%;" />

### The Docker daemon

The Docker daemon (`dockerd`) listens for Docker API requests and manages Docker objects such as images, containers, networks, and volumes. A daemon can also communicate with other daemons to manage Docker services.

Docker 守护进程监听并反馈API接口，管理docker对象例如：镜像，容器，网络，数据卷。守护进程还可以与其他守护进程沟通形成一个容器集群。

### The Docker client 客户端

The Docker client (`docker`) is the primary way 主要的方式 that many Docker users interact with Docker. When you use commands such as `docker run`, the client sends these commands to `dockerd`, which carries  them out. The `docker` command uses the Docker API. The Docker client can communicate with more than one daemon.

Docker客户端作为和docker守护进程交流的主要方式。当你使用命令行例如docker run，客户端采用Docker API去发送指令给处理的守护进程。并且可以连接不止一个docker守护进程。

### Docker registries 登记，注册，有点类似Github

A Docker *registry* stores Docker images. 

Docker registry 存储着docker的镜像

Docker Hub is a public registry that anyone can use, and Docker is configured 配置 to look for 寻找 images on Docker Hub by default.

Docker Hub 是一个公共的注册中心，所有人都可以使用。Docker默认是在Docker hub寻找镜像。

 You can even run your own private registry. If you use Docker Datacenter (DDC), it includes Docker Trusted Registry (DTR).

你可以使用Docker 数据中心DDC包含（DTR Docker 可信注册）去搭建自己的私人镜像中心。

When you use the `docker pull` or `docker run` commands, the required images are pulled from your configured registry. 

当你使用pull 或者 run 命令的时候，请求的镜像从你配置的镜像中心中拉去。

When you use the `docker push` command, your image is pushed to your configured registry.

当你提交时，也是提交到你配置的镜像中心中。

### Docker objects 对象

When you use Docker, you are creating and using images, containers, networks, volumes, plugins, and other objects. This section 部分 is a brief 检验 overview 概述 of some of those objects.

当你使用Docker，你创建镜像，容器，网络，数据卷，插件，和其他对象。这部分简要的介绍下这些对象



#### IMAGES 镜像

An *image* is a read-only template with instructions 指令，说明 for creating a Docker container. 

镜像是一个只读的模版指令用于创建Docker容器。

Often, an image is *based on* another image, with some additional customization. 

通常一个镜像是以另外一个镜像为基础加上一点自定义。

For example, you may build an image which is based on the `ubuntu` image, but installs the Apache web server and your application, as well as the configuration details needed to make your application run.

例如，你使用ubuntu系统镜像为基础，并在之上安装了web服务器和你的应用程序之后形成心新的镜像。这个过程就像你在开发你的应用程序一样。？**存疑**



You might create your own images or you might only use those created by others and published in a registry. 

你可以基于哪些公开提交到镜像中心的镜像创建你自己的镜像

To build your own image, you create a *Dockerfile* with a simple syntax 语法 for defining the steps needed to create the image and run it. 

创建自己的镜像，dockerfile可以让你使用简单的语法去定义每一步你需要的操作，然后通过它去构建你的镜像。

Each instruction in a Dockerfile creates a layer in the image. 

在Dockerfile的每个指令都会创建**一层镜像**

When you change the Dockerfile and rebuild the image, only those layers which have changed are rebuilt.

当你修改了dockerfile后重新构建你的镜像时，只有**那些被修改的层会被改变**

 This is part of what makes images so lightweight, small, and fast, when compared to other virtualization technologies.

这是为什么对比其他虚拟技术镜像可以如此轻量级，小巧，和快速。吹，就是一顿吹

#### CONTAINERS 容器

A container is a runnable instance of an image. 

容器是镜像的一个可运行的实例。

You can create, start, stop, move, or delete a container using the Docker API or CLI.

你可以通过命令行工具或者Docker API 去创建，开启，关闭，**移动**，或者删除。

You can connect a container to one or more networks, attach storage to it, or even create a new image based on its current state.

你可以在这个容器基础上创建新的镜像。也可以让它连接更多的网络或者挂载存储设备给他。

By default, a container is relatively 相当的 well isolated from other containers and its host machine. 

但是默认情况下，容器相对于其他容器或者宿主机其实是相当独立的存在。

You can control how isolated a container’s network, storage, or other underlying subsystems are from other containers or from the host machine.

你可以控制容器的网络或者存储设备与运行在其他容器的子系统或者宿主机的隔离级别。

A container is defined by its image as well as any configuration options you provide to it when you create or start it. 

一个容器被两方面定义：1是他的镜像，2是创建和开启它时候的配置选项 例如 -p3306:3306 端口映射等

When a container is removed, any changes to its state that are not stored in persistent storage 持续存储（就是说被本地存储起来不会丢失的意思） disappear.

当一个容器被移除，所有有关它的改变都会消失，不会被实际存储

##### Example `docker run` command 一个很简单的docker容器运行指令

The following command runs an `ubuntu` container, attaches 附加 interactively 交互 to your local command-line session, and runs `/bin/bash`.

这个指令使用了ubuntu镜像创建了一个容器并运行。

```
$ docker run -i -t ubuntu /bin/bash
```

When you run this command, the following happens (assuming you are using the default registry configuration):

当你执行这个命令的时候会发生的事情（假设你使用的所有配置都是默认的）

1. If you do not have the `ubuntu` image locally, Docker pulls it from your configured registry, as though you had run `docker pull ubuntu` manually. 
2. Docker creates a new container, as though you had run a `docker container create` command manually.
3. Docker allocates a read-write filesystem to the container, as its final layer. This allows a running container to create or modify files and directories in its local filesystem.
4. Docker creates a network interface to connect the container to the default network, since you did not specify any networking options. This includes assigning an IP address to the container. By default, containers can connect to external networks using the host machine’s network connection.
5. Docker starts the container and executes `/bin/bash`. Because the container is running interactively and attached to your terminal (due to the `-i` and `-t` flags), you can provide input using your keyboard while the output is logged to your terminal.
6. When you type `exit` to terminate the `/bin/bash` command, the container stops but is not removed. You can start it again or remove it.



1. 如果你本地没有`ubuntu`的镜像，Docker会去你配置的镜像中心拉去。就像你手动执行`docker pull ubuntu`一样
2. Docker创建一个新的容器，就像你手动执行`docker container create`一样
3. Docker分配一个文件读写系统给容器，作为最后一层。文件读写系统允许执行中的容器在它的本地目录上创建或者修改文件。
4. 如果你没有指定特定连接网络的配置，Docker会创建一个网络接口去连接默认的网络。这个包括分配容器的IP地址。默认情况下容器**可以**通过宿主机的网络去连接外部网。
5. Docker开启一个容器，并且运行 /bin/bash 。由于你执行了 -i 和 -t 你可以在终端上与容器交互。这样你的键盘就是输入设备，终端就是输出设备。
6. 当你执行exit命令在终端上的时候。容器会停止但是不会被移除。你可以对它进行重新启动或者移除。

#### SERVICES 集群

Services allow you to scale containers across multiple Docker daemons, which all work together as a *swarm* with multiple *managers* and *workers*. 

服务允许你把许多容器按比例的部署在多个Docker守护进程上。他们运行在一个集群中集群里有多个管理者和工作者。

Each member of a swarm is a Docker daemon, and all the daemons communicate using the Docker API. 

swarm中的每一个Docker守护进程使用Docker API互相联系。

A service allows you to define the desired state, such as the number of replicas of the service that must be available at any given time. 

集群可以定义你的一些要求状态，例如多少分片镜像必须存活在集群中。这样可以保证数据安全也可以提高吞吐量。

By default, the service is load-balanced across all worker nodes.

默认情况下，所有服务都会被做负载均衡

To the consumer, the Docker service appears to be a single application. 

但是这一切对于使用者来说就像操作一个单体应用一样简单。

Docker Engine supports swarm mode in Docker 1.12 and higher.

这个集群必须运行在Docker 1.12或者更高版本中。

## The underlying technology[🔗](https://docs.docker.com/get-started/overview/#the-underlying-technology)

关于Docker的底层技术

Docker is written in [Go](https://golang.org/) and takes advantage of several features of the Linux kernel to deliver its functionality.

Docker是使用Go语言和使用了Linux 内核的一些特性去实现功能。

### Namespaces 名字空间

Docker uses a technology called `namespaces` to provide the isolated workspace called the *container*. 

Docker的容器是由一个叫`名字空间`的技术去提供一个隔离的工作空间

When you run a container, Docker creates a set of *namespaces* for that container.

当你开启容器，Docker给你创建了**一套**`名字空间`，注意是一套

These namespaces provide a layer of isolation. 

这些名字空间提供了一个隔离层。

Each aspect of a container runs in a separate 单独的 namespace and its access is limited to that namespace.

每一个容器运行在一个单独的名字空间中，并且它的权限只在这个名字空间中。

Docker Engine uses namespaces such as the following on Linux:

Docker引擎使用了Linux的下列名字空间

- **The `pid` namespace:** Process isolation (PID: Process ID).
- **The `net` namespace:** Managing network interfaces (NET: Networking).
- **The `ipc` namespace:** Managing access to IPC resources (IPC: InterProcess Communication).
- **The `mnt` namespace:** Managing filesystem mount 爬 points (MNT: Mount).
- **The `uts` namespace:** Isolating kernel and version identifiers. (UTS: Unix Timesharing System).



- `pid` ：用于线程隔离
- `net`：管理网络接口 
- `ipc`：管理对IPC资源的访问（IPC：线程之间的联系）
- `mnt`：管理文件系统挂载点
- `uts`：隔离的内核和版本鉴定（UTS：unix 时间分享系统）

### Control groups 控制组

Docker Engine on Linux also relies 信任 on another technology called *control groups* (`cgroups`). 

Docker引擎在Linux中也依赖叫控制组的技术

A cgroup limits an application to a specific set of resources. 

控制组控制着应用程序的一系列资源

Control groups allow Docker Engine to share available hardware resources to containers and optionally enforce limits and constraints. 

控制组允许Docker引擎去分享可用的硬件资源给容器和控制

For example, you can limit the memory available to a specific container.

例如：你可以限定你的容器的可用内存

PS：这块地方应该是说通过cgroup技术去分配宿主资源给容器们

### Union file systems

Union file systems, or UnionFS, are file systems that operate by creating layers, making them very lightweight and fast. 

联盟文件系统，使用层的概念让它非常的轻量级和快速

Docker Engine uses UnionFS to provide the building blocks for containers. 

Docker引擎使用UnionFS去实现

Docker Engine can use multiple UnionFS variants, including AUFS, btrfs, vfs, and DeviceMapper.

Docker也可以使用多种联合文件系统，包括 AUFS, btrfs, vfs, and DeviceMapper.

PS：这个应该就是容器一层一层的功能实现基础

### Container format 容器格式

Docker Engine combines the namespaces, control groups, and UnionFS into a wrapper called a container format. 

Docker引擎结合了名字空间，控制组，联合文件系统，打包成一个叫容器格式的东西

The default container format is `libcontainer`.

默认的容器格式是 lib container

 In the future, Docker may support other container formats by integrating with technologies such as BSD Jails or Solaris Zones.

在未来，Docker也许会支持通过其他技术像BSD Jails 或者 SZ 实现的容器格式

PS：容器格式就是一套实现Docker引擎的底层技术