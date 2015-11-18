---
layout: post
title: 如何在Ubuntu上安装最新版本的Git
---
在阿里云申请了一个15天试用版的云服务器 (ECS)，操作系统选择的Ubuntu 14.04，然后就开始了艰辛的Linux学习历程，要学习的东西真的很多呀。

在安装Git的时候发现默认APT源中包含的Git版本太低了v1.9.1，而当前[Git](http://git-scm.com/)的最新版本是v2.6.3，于是就开始搜索如何安装最新版本的Git。

通过[百度](http://www.cnblogs.com/zhcncn/p/4030078.html)和[Google](http://stackoverflow.com/questions/19109542/installing-latest-version-of-git-in-ubuntu)都搜索到了相同的解决办法：

```bash
sudo add-apt-repository ppa:git-core/ppa
sudo apt-get update
sudo apt-get install git
```

这里就遇到两个问题需要搞清楚：

1. add-apt-repository 是做什么用的？
原来它是一个[脚本](https://help.ubuntu.com/community/add-apt-repository)，专门用来把Personal Package Archives(PPA)添加到当前的源列表里面。

2. ppa:git-core/ppa 又是个啥？
原来这是Ubuntu的[个人软件包档案](https://help.launchpad.net/Packaging/PPA)的表示方式
> Personal Package Archives (PPA) allow you to upload Ubuntu source packages to be built and published as an apt repository by Launchpad. You can find out more about PPAs and how to use them in our help page.

在执行第一行命令的时候返回一个错误：

```bash
sudo: add-apt-repository: command not found
```

去掉sudo后又提示一个不同的错误：

```bash
The program 'add-apt-repository' is currently not installed. You can install it by typing:
apt-get install software-properties-common
```

software-properties-common又是个啥？官方站点的[解释](https://apps.ubuntu.com/cat/applications/software-properties-common/)是这样的：
> This software provides an abstraction of the used apt repositories. It allows you to easily manage your distribution and independent software vendor software sources.
> This package contains the common files for software-properties like the D-Bus backend.

终于我的Git变成了最新版本：

```bash
git --version
git version 2.6.3
```

:v:
