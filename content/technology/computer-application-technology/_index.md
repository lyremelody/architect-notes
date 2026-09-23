---
type: docs
title: '计算机应用'
linkTitle: '计算机应用'
weight: 18
bookCollapseSection: true
date: 2021-11-29
menu:
  main:
    weight: 30
    pre: <i class='fa fa-cogs'></i>
cascade:
  type: "docs"
isCJKLanguage: true
params:
  author: lyremelody
---

#### 负载均衡
* LVS(Linux Virtual Server)
* nginx

#### 3.3.2 云技术 (Cloud Technology)
#### 3.3.3 云原生技术(Cloud Native)
##### 3.3.3.1 容器(Container)
* [Podman vs Docker，有哪些差异？](./cloud-native/podman-vs-docker.md)
* Docker
  * [那些年踩过的坑--Docker篇](./cloud-native/docker/docker-practice-20170713.md)
  * [那些年踩过的坑--Docker篇（二）数据持久化](./cloud-native/docker/docker-practice-20180204.md)
* Kubernetes
  * [Kubernetes是什么？](./cloud-native/kubernetes/what-is-kubernetes.md)
  * [Kubernetes 核心概念](./cloud-native/kubernetes/kubernetes-concepts.md)
  * [使用 kubectl](./cloud-native/kubernetes/kubernetes-use-kubectl.md)
  * [Pod 健康检查](./cloud-native/kubernetes/kubernetes-pod-health-check.md)
* Helm
  * [Helm是什么？](./cloud-native/helm/what-is-helm.md)

##### 微服务框架(Microservice Framework)

##### 服务网格(Service Mesh)

##### 分布式应用运行时(Distributed Application Runtime)
* Dapr
* Layotto

##### 资料(链接)收集
* **公司/社区资料**
  1. [CNCF，云原生计算基金会](https://www.cncf.io/)
  2. [云原生技术公开课](https://edu.aliyun.com/roadmap/cloudnative)，阿里云
* **博客/文章**
  1. [云原生已来，只是分布不均](https://mp.weixin.qq.com/s/apihIHmPwyVdZZi5d7U0Wg)，2020-06-17
  2. [云原生科普丨云原生才是「吞噬世界」的那条大鱼...](https://mp.weixin.qq.com/s?__biz=MjM5NTEwMTAwNg==&mid=2650219017&idx=1&sn=b74b0b438ad9b6883fc1298bb11ba7c4&chksm=befe22288989ab3ee981797797205053d21bfd511feb2d1169fbae9d9e24feadc1c887b79480&scene=0&xtrack=1)，2020-02-05
  3. [为何云原生在吞噬世界](http://www.sohu.com/a/353123831_465914)，2019-11-11
  4. [谷歌：云原生架构的5条原则](https://www.infoq.cn/article/B5Zk1p*8SGk5ZIVk27gv)，2019-07-08
  5. [畅谈云原生（下）：云原生的飞轮理论](https://www.infoq.cn/article/HMizcSG_FgcJKGzkE08L)，2019-03-01
  6. [畅谈云原生（上）：云原生应用应该是什么样子？](https://www.infoq.cn/article/fA42rfjV*dYGAvRANFqE)，2019-02-27
  7. [Cloud Native Application Maturity Model](https://dzone.com/articles/cloud-native-application)，2015-03-27
* **笔记**
  1. [CloudNative学习笔记](https://skyao.io/learning-cloudnative/)，skyao
* **Kubernetes资料**
  1. [深入剖析Kubernetes@极客时间](https://time.geekbang.org/column/intro/116)
  2. [云原生技术公开课](https://edu.aliyun.com/roadmap/cloudnative)，阿里云
  3. [Kubernetes指南](https://feisky.gitbooks.io/kubernetes/)，很好的中文资料
  4. [Kubernetes Handbook](https://jimmysong.io/kubernetes-handbook/)，很好的中文资料
  5. [Kubernetes中文社区](https://www.kubernetes.org.cn/)
  6. [Kubernetes Learning Path](https://azure.microsoft.com/en-us/resources/kubernetes-learning-path/)，Microsoft Azure
  7. [Kubernetes production best practices](https://learnk8s.io/production-best-practices)，learnk8s.io
  8.  [Kubernetes troubleshooting flowchart](https://learnk8s.io/troubleshooting-deployments)，learnk8s.io
* **Helm资料**
  1. [Helm 用户指南](https://whmzsu.github.io/helm-doc-zh-cn/)，中文资料
* **其他**
  1. [awesome-cloud-native](https://github.com/rootsongjc/awesome-cloud-native)
  2. [Architecting Cloud-Aware Applications Rev. 1.0](http://www.oaca-project.org/wp-content/uploads/2018/07/Architecting-Cloud-Aware-Applications-Best-Practices-Rev-1.0.pdf)，OPEN DATA CENTER ALLIANCE，PDF 


#### 数据库(Database)
##### 关系数据库(Relational Database)
* MySQL
* MariaDB

##### NoSQL
* Redis
* MongoDB
* Etcd

#### 消息队列(Message Queue)
* [什么是消息队列？](./infrastructure/what-is-message-queue.md)
* Kafka
* NSQ
* RabbitMQ

#### 搜索引擎(Search Engine)
* [初识搜索引擎](./infrastructure/search-engine-20180427.md)
* Elasticsearch
  * [Elasticsearch Rally](./infrastructure/elasticsearch-rally-20180123.md)
  * [Elasticsearch 热温数据迁移验证](./infrastructure/elasticsearch-hot-warm-20181211.md)
* OpenSearch

#### 通用人工智能(Artificial General Intelligence)

### 故障排查(Troubleshooting)
* [Kubernetes Troubleshooting](./troubleshooting/kubernetes-troubleshooting.md)


### 其他技术问题(Others)
* [全球化系统中的日期时间处理问题](./others/problems/globalization-datatime.md)
