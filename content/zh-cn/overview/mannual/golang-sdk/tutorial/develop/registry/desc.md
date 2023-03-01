---
aliases:
    - /zh/docs3-v2/golang-sdk/tutorial/develop/registry/desc/
    - /zh-cn/docs3-v2/golang-sdk/tutorial/develop/registry/
description: 了解注册中心
title: 了解注册中心
type: docs
weight: 1
---





## 什么是注册中心

所谓的注册中心，可以简单的理解为手机的通讯录。通讯录的目的是方便我们记录朋友、同事、家人等联系方式。一般的存储方式格式都是：姓名--联系方式，当我们需要联系某个人时，打开我们的通讯，找到他的名字，拨打电话。

注册中心要做的事情，也是类似的。它记录了服务和服务地址的映射关系。在分布式架构中，服务会注册到这里，当服务需要调用其它服务时，就到这里找到服务的地址，进行调用。


## 为什么需要注册中心

随着单体应用拆分，首当面临的第一份挑战就是服务实例的数量较多，并且服务自身对外暴露的访问地址也具有动态性。以及微服务架构的发展，越来越多的设计中采用微服务架构。在微服务中首先需要面对的问题就是不同的服务之间如何进行通信。在单体服务中如果不同的服务之间需要通信，一般就是服务将接口暴露，然后其他的服务通过配置文件记录依赖服务的地址即可。在分布式系统中，这种方案是明显不合适的。分布式系统会变得更加复杂，比如：

- 新服务上线后，如何被及时发现
- 服务宕机后，如何及时下线
- 服务如何有效的水平扩展
- 服务发现时，如何进行路由
- 服务异常时，如何进行降级

这里问题的解决都依赖于注册中心。
为了有效的解决这些问题，我们可以把这些问题全部交给注册中心去解决，这样，不同的服务只需要关注自身的业务和设计实现即可。


## dubbo-go支持的注册中心

### Nacos
Nacos /nɑ:kəʊs/ 是 Dynamic Naming and Configuration Service的首字母简称，一个更易于构建云原生应用的动态服务发现、配置管理和服务管理平台。

Nacos 致力于帮助您发现、配置和管理微服务。Nacos 提供了一组简单易用的特性集，帮助您快速实现动态服务发现、服务配置、服务元数据及流量管理。

Nacos 帮助您更敏捷和容易地构建、交付和管理微服务平台。 Nacos 是构建以“服务”为中心的现代应用架构 (例如微服务范式、云原生范式) 的服务基础设施。

官网：https://nacos.io/

### Zookeeper
ZooKeeper 是 Apache 软件基金会的一个软件项目，它为大型分布式计算提供开源的分布式配置服务、同步服务和命名注册。

ZooKeeper 的架构通过冗余服务实现高可用性。

Zookeeper 的设计目标是将那些复杂且容易出错的分布式一致性服务封装起来，构成一个高效可靠的原语集，并以一系列简单易用的接口提供给用户使用。

一个典型的分布式数据一致性的解决方案，分布式应用程序可以基于它实现诸如数据发布/订阅、负载均衡、命名服务、分布式协调/通知、集群管理、Master 选举、分布式锁和分布式队列等功能。

官网：https://zookeeper.apache.org/

### Polaris
北极星是腾讯开源的服务治理平台，致力于解决分布式和微服务架构中的服务管理、流量管理、配置管理、故障容错和可观测性问题，针对不同的技术栈和环境提供服务治理的标准方案和最佳实践。下面介绍北极星的应用场景、功能特性、系统组件和常见问题。


官网：https://polarismesh.cn/