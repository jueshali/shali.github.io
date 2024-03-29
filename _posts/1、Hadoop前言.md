---
layout:     post
title:      Hadoop前言
subtitle:   file类
date:       2019-6-1
author:     LPC
header-img: img/HelloWorld.png
catalog: true
tags:
    - hadoop
---

# Hadoop前言

- [Hadoop前言](#hadoop%e5%89%8d%e8%a8%80)
  - [大数据](#%e5%a4%a7%e6%95%b0%e6%8d%ae)
  - [Hadoop](#hadoop)
    - [是什么](#%e6%98%af%e4%bb%80%e4%b9%88)
    - [有什么优势](#%e6%9c%89%e4%bb%80%e4%b9%88%e4%bc%98%e5%8a%bf)
    - [Hadoop1.x 和 hadoop2.x的区别](#hadoop1x-%e5%92%8c-hadoop2x%e7%9a%84%e5%8c%ba%e5%88%ab)
  
## 大数据

大数据指在规定的时间内使用常规软件无法处理的数据集！它具有数据集通常有以下特点：

- 海量：数据量很大，以往的传统数据库根本存不下，存下来也难以处理
- 高增长率：大数据的增长速度极快，双十一一天的数据就无限大。
- 形式多样：除了结构化数据，还有非结构化数据和半结构化数据
- 低价值：大数据单位数据量的价值量远远比不上传统的数据，但胜在以量取胜。

## Hadoop

### 是什么

Hadoop狭义上指的是Hadoop框架，包括HDFS，yarn和Map-Reduce.在广义上指的是以Hadoop为核心的大数据生态体系。其中我认为Hadoop的核心是HDFS，HDFS是一个适合大数据存储的文件系统，可靠性高。yarn是从MapReduce中独立出来的，主要是用于资源调度。Map-Reduce是一个编程模型，适用于本地大数据的计算。

### 有什么优势

1. 高可靠：  每份数据在HDFS存储时，都会存储多个副本，由HDFS自动维护副本数！
2. 易扩展：  当集群的存储能力不够或计算能力不够，都可以方便第向集群中添加机器！
3. 高容错：  Map-Reduce在计算时，可以自动采取容器机制，一旦有节点执行的计算任务失败，会自动分配到其他节点执行！
4. 高效：    MR在运行时是分布式运算，效率高(对比传统的计算方式)！

### Hadoop1.x 和 hadoop2.x的区别

1.x的MapReduce编程模型，既负责计算，也负责为计算的程序申请和调度硬件资源！
弊端：  所有的程序必须按照MR的模型进行编写，才可以使用Hadoop集群中的硬件资源！

2.x时，将资源的调度从MR中分离，使用YARN进行资源的调度。MR只负责一个计算模型！
好处：  一个Hadoop集群，在运行自身的MR程序时，可以从YARN申请资源！
其他的计算框架，例如Spark，Flink，Tez等也可以对接YARN，来申请资源进行运算！
2.x开始支持HA(高可用的Hadoop)

虽然现在出了Hadoop3，但这次我的学习主要集中于hadoop2
Hadoop3 相比于Hadoop2只做出以下改进
HDFS改进：支持erasure编码，支持超过两个namenode，数据均衡，多个服务端口发生变化，变化不是那么大。
