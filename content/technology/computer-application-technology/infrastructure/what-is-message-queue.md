---
title: '什么是消息队列？'
linkTitle: '什么是消息队列？'
type: 'docs'
weight: 1641
bookFlatSection: true
bookHidden: false
date: 2018-04-27
isCJKLanguage: true
params:
  author: lyremelody
---

## 1 对于队列的理解

队列是一种「先进先出」数据结构。

具体见的[《数据结构-队列》](../../computer-theory/data-structures-and-algorithms/stack-and-queue.md)

## 2 对于消息队列的理解

**消息队列**，**Message Queue**，也是「队列」。

「消息队列」用于实现进程间通信或同一进程的不同线程间的通信，它通过队列来存储和处理一系列的用户输入，消息会保存在队列中，直到接收者取回它。

「消息队列」提供异步的通信协议，每一个队列的记录包含详细的数据，包含发生的时间、输入设备的种类、以及特定的输入参数。

消息的发送者和接收者不需要同时与消息队列交互。

## 3 开源消息队列

### RabbitMQ

官网：[https://www.rabbitmq.com/documentation.html](https://www.rabbitmq.com/documentation.html)

### RocketMQ

官网：[https://rocketmq.apache.org/docs/quick-start/](https://rocketmq.apache.org/docs/quick-start/)

RocketMQ 中国开发者中心：[http://rocketmq.cloud/zh-cn/](http://rocketmq.cloud/zh-cn/)

### Kafka

官网：[http://kafka.apache.org/documentation/](http://kafka.apache.org/documentation/)

### ActiveMQ

官网：[https://activemq.apache.org/](https://activemq.apache.org/)

### ZeroMQ

官网：[https://zeromq.org/get-started/](https://zeromq.org/get-started/)

### Pulsar

官网：[https://pulsar.apache.org/](https://pulsar.apache.org/)

### NSQ

官网：[https://nsq.io/](https://nsq.io/)

## 4 其他关注的消息队列

### KubeMQ

官网：[https://kubemq.io/](https://kubemq.io/)

## 5 参考资料

1. [Wiki - 消息队列](https://zh.wikipedia.org/wiki/%E6%B6%88%E6%81%AF%E9%98%9F%E5%88%97)
