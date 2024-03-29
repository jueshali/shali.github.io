---
layout:     post
title:      Hadoop的安装
subtitle:   file类
date:       2019-6-1
author:     LPC
header-img: img/HelloWorld.png
catalog: true
tags:
    - hadoop
---

# Hadoop的安装

- [Hadoop的安装](#hadoop%e7%9a%84%e5%ae%89%e8%a3%85)
  - [安装前准备](#%e5%ae%89%e8%a3%85%e5%89%8d%e5%87%86%e5%a4%87)
  - [软件的安装和环境变量的配置](#%e8%bd%af%e4%bb%b6%e7%9a%84%e5%ae%89%e8%a3%85%e5%92%8c%e7%8e%af%e5%a2%83%e5%8f%98%e9%87%8f%e7%9a%84%e9%85%8d%e7%bd%ae)
    - [软件的安装](#%e8%bd%af%e4%bb%b6%e7%9a%84%e5%ae%89%e8%a3%85)
    - [环境变量的配置](#%e7%8e%af%e5%a2%83%e5%8f%98%e9%87%8f%e7%9a%84%e9%85%8d%e7%bd%ae)
  - [示例程序的运行](#%e7%a4%ba%e4%be%8b%e7%a8%8b%e5%ba%8f%e7%9a%84%e8%bf%90%e8%a1%8c)
  - [走过的坑解决](#%e8%b5%b0%e8%bf%87%e7%9a%84%e5%9d%91%e8%a7%a3%e5%86%b3)


在对Hadoop有大概的了解后就要开始Hadoop的安装了，Hadoop安装有本地模式，单机分布式模式和多机分布式模式。
学一个新事物讲究一个由易到难，但是对复习而言，直接复习最难的效率最高，因此本篇文章直接开始多机分布式的安装。且使用的虚拟机为virtual box.

## 安装前准备

1. 网络环境配置
   - 防火墙关闭
   - 配置host
   - 配置hosts
   - 配置网卡信息
2. 多台机器免密登录设置
   - ssh分发
   - xsync脚本的编写和使用
  
## 软件的安装和环境变量的配置

### 软件的安装

Java 安装：解压即可\
Hadoop 安装：解压即可

### 环境变量的配置

## 示例程序的运行

## 走过的坑解决

- 节点的datanode启动不了， 这个问题可能我遇到过两次，两次的原因各不 相同

1. 重复格式化。建议重装，或者查其他博客
2. hadoop的安装目录下有些文件的所有权属于root，导致无法启动解决方法     sudo chown -R 用户名 hadoop安装路径

- 换地区后网路不能使用\
由于virtual box采用的桥接，这个问题非常常见，解决方法是首先改host,hosts,网卡配置。其次重新配置SSH，由于hadoop通过主机名通信，因此其他问题不会发生。
