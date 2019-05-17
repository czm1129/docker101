# Docker入门与实践

刘斌，软件工程师@Alauda
2015年8月


# 课程简介

- 目的
- 对象
- 内容

# 对象用户

- Linux
- Git（GitHub）

# 参考资料

- 官方文档（https://docs.docker.com/）
- 《第一本Docker书》

# 什么是Docker

- Build, Ship, Run
- An open platform
- For distributed applications
- For developers and sysadmins
- https://www.docker.com
- https://www.github.com/docker/docker

# 什么是Docker

- 开放平台
- 容器技术
- 交付标准
- 开发流程

# Docker产生背景

- 云计算技术
- 软件架构
- 积累的问题

# 云计算技术

- 虚拟化技术
- IaaS(AWS)
- PaaS(Heroku)
- 网络技术（SDN/Open vSwitch/Overlay网络/隧道技术）

# 观点

- An EC2 instance is not a server—it’s a building block.
- Re:Invent，Amazon’s CTO, Werner Vogels

# 软件架构

- SOA
- 微服务
- 12-Factor App
- Blue-green Deployment
- Golden Image

# 积累问题

- 依赖地狱和一致环境
- Hardware
- OS
- Library(Version etc.)
- Rails(3/4),Ruby(1.8/1.9/2.0/2.1)


# 12-Factor App

- Codebase
- Dependencies
- Config
- Build, release, run
- Processes
- Port binding
- Dev/prod parity
- Logs

# Docker的解决方案

- 集装箱思想
- 标准化（大小、运输方式等，接口统一）
- 隔离（互不干扰、影响）

# Docker的解决方案

![](./images/docker-solution.png)

# 什么是容器？

- 一组进程在独自的OS环境
- 独立文件内容
- 独立网络环境（hostname，IP地址等）
- CPU、内存分配

# 只是容器？

- Docker（2013）
- lmctfy（2013）
- LXC（2008）
- RHEL OpenVZ（2005）
- Solaris Zones（2004）
- FreeBSD jail（2000）
- chroot（????）

# 只是容器？

- chroot（1979/1982）

# 为什么Docker吸引人

- 简单
- 轻量
- 隔离
- 移植性
- 以应用为中心
- 版本化
- 重用
- Immutable

# 简单一句话

- 从阳春白雪，到下里巴人
- 从专业运维、SA专家，到前端、设计师

# 和虚拟机相比

![](./images/docker-vs-vm.png)

# 和虚拟机相比

- 实现原理
- 启动时间
- 可启动实例数量
- overhead
- 安全性（隔离）
- 磁盘空间

# Docker实现原理

- 核心Linux内核功能
- Control Groups（cgroups）
- Namespace
- iptables
- Union File System

# 安全相关内核功能

- Kernel Capability
- 对进程持有的特权进行细粒度管理的机制
- 系统时间，内核模块，硬件设备
- SELinux(Security-Enhanced Linux/RedHat系Linux)
- Apparmor(简单/Debian/Ubuntu)

# cgroups

- Control groups
- 按资源划分等级的不同组内
- 共享硬件
- 对资源进行限制
- 记账
- 伪文件系统的实现方式

# cgroups

- blkio： 块设备读写限制（Read <= N bytes/sec）
- cpu： 对CPU调度器的限制
- cpuset： 多核下对CPU访问的控制
- cpuacct: CPU accounting controller
- devices： 对设备的控制
- freezer：处理的暂停和恢复
- memory： 控制内存资源的使用
- net_cls： 使用等级识别符（classid）标记网络数据包，可允许 Linux 流量控制程序（tc）识别从具体 cgroups 中生成的数据包。
- net_prio： 对不同网络接口通信的优先级别的设置


# Namespaces

- pid： 进程（PID）隔离（2.6.24）
- net： 网络隔离（2.6.26）
- ipc： IPC隔离，POSIX消息队列，共享内存（2.6.19）
- mnt： 挂载点隔离（2.4.19）
- uts： hostname，NIS域名（UTS: Unix Timesharing System）（2.6.19）
- user： 用户隔离（3.8）

# Docker适用场景

- 开发
- 测试
- 部署
- CI/CD
- PaaS/CaaS
- 只有想不到，没有做不到
- 还有人用来装Eclipse呢

# Docker将会给这些领域带来影响

- Software Development
- Deploy & Delivery
- DevOps

# Docker带来的收益

- 快速交付（交付标准）
- 轻松部署
- 快速缩、扩容
- 提高资源利用率（高密度、满负荷）
- 提升软件工程师满意度

# Docker历史

- 优秀的产品背后都有一家伟大的公司
- docCloud（YCombinator），2013年1月内部项目
- 2013年3月，在PyCon US首次公开
- 2013/3/27 Docker 0.1
- 2014/6 Docker 1.0
- 几乎每月一个版本
- 2015年8月，Docker 1.8发布
- 2014.7 C轮融资4000万美元
- 2015.4 D轮融资9500万美元

# 支持平台

- Linux
- Boot2Docker（Windows 、 OS X）
- Windows native

# Docker 组件

- Docker Engine 或 “Docker”
- 创建和运行Docker容器，运行平台。
- Docker Hub
- 托管的Registry，镜像托管服务，无需安装，只需要注册一个账号。
- Docker Registry
- 开源的Docker镜像分发服务（存储、下载）。


# Docker 组件

- Docker Machine
- 本地或者云端自动容器环境provisioning工具。
- Docker Compose
- 多容器应用管理
- Docker Swarm
- 容器集群和调度管理工具

# Docker 组件

- Kitematic
- 桌面GUI管理程序
- Docker Toolbox
- 替代Boot2Docker

# Docker 组件

- Docker Trusted Registry(DTR)
- 私有专用镜像Registry。
- Docker Subscription
- Docker订购，增值服务；
- 在整个部署、分发的生命周期提供帮助
- 包括DTR
- 部署到公有或者私有云

# 我们不会讲

- Docker ToolBox/Kitematic： 有了本课程基础，应对Kitematic应该小事一桩
- DTR： 我们会讲Registry
- Docker Subscription：
- 1. 我们会讲 Registry
- 2. 都花钱买Subscription了，就享受服务吧

# Docker Engine架构

- C/S结构
- Remote API（RESTful）
- TLS支持

![](./images/docker-arch.png)

# Docker in Linux

![](./images/docker-daemon-cli.png)

# Libcontainer

- Container format
- Execution driver
- 将cgroups，Namespace，Union FS集成到一起使用

![](./images/docker-libcontainer-lxc.png)

# Docker Engine核心概念

- Docker镜像（image）
- Docker容器（containers）
- Docker Registry

# 镜像

- 文件系统
- 只读、静态
- 层（Layer）
- 父子关系（Parent Image）
- 基础镜像（Base Image）
- ID（64字符，256bit存储）

# 容器 - Container

- 创建、运行和退出
- ID（和镜像ID类似）

![](./images/docker-filesystem.png)

# Registry

- 托管镜像仓库（repositories of images）
- Registry API
- Docker Hub和私有Registry
- 码头上的仓库

# 课程演习环境

- Vagrant
- CentOS 7
- Docker 1.7.1
- 灵雀云（alauda.cn）

# Docker For Non-Linux

- Boot2Docker
- Toolbox

# Docker in Non-Linux

![](./images/docker-in-osx.png)

# Docker Toolbox (Docker 1.8)

- Docker Client
- Docker Machine
- Docker Compose (Mac only)
- Docker Kitematic
- VirtualBox

![](./images/docker-toolbox-logo.png)

# VirtualBox和Vagrant

- 虚拟机
- 虚拟机管理软件
- hashicorp
- Serf/Consul/Packer等工具

# Vagrant

- vagrant init chef/centos-7.0
- vagrant up
- vagrant ssh

# Vagrant

- 下载centos7镜像：http://pan.baidu.com/s/1kT7u5oF
- vagrant box add chef/centos-7.0 opscode_centos-7.0_chef-provisionerless.box
- 执行上一页命令

# 不必一切从头开始

- git clone https://github.com/liubin/docker101

# Vagrantfile

- box
- forwarded_port
- synced_folder

# 安装Docker

- 64位Linux
- 内核3.10

# 安装Docker

- $ sudo yum update
- $ curl -sSL https://get.docker.com/ | sh
- $ sudo systemctl enable docker
- $ sudo systemctl start docker
- $ sudo docker -v
- Docker version 1.8.1, build d12ea79

# 设置镜像加速

- 灵雀云（https://console.alauda.cn）
- --registry-mirror=http://liubin.m.alauda.cn

# 答疑

- https://github.com/liubin/docker101
- Alauda社区

# 课后作业

- 浏览官方文档
- 安装Docker
- 注册alauda.cn账户

