---
title: Hexo+GitHub+Netlify构建使用Hexo-Theme-Sakura主题的静态博客（完全免费）
author: eightoneeight
avatar: https://i.loli.net/2021/03/20/LtDwY8SbUnAPHN9.jpg
authorLink: www.worldeightclient.top
authorAbout: 你猜哟
authorDesc: 你猜哟
categories: 技术
date: 2021-03-22 22:16:01
comments: true
tags: 
keywords: Sakura
description: 搭建和本博客一样的Hexo博客
photos: 
---
# 1 前言

网络上的Hexo教程非常多，但是我创作这一个教程的目的是针对想要搭建Sakura主题的博主提供一个完善的从头到尾搭建、优化到发布的全过程的详细教程

# 2 准备

## 2.1 Why Hexo/GitHub/Netlify?

Hexo是一个基于 Node.js 的静态博客框架，只需要很简单的配置就可以通过庞大的社区、大量的主题和插件等进行写作；GitHub 是免费的，也是大家最常使用的；Netlify 是因为相比于 GitHub Pages 它访问速度更快，而且也不需要付费。

## 2.2 Node.js 安装

前往[这里（英文站）](https://nodejs.org/en/)或者[中文站（推荐）](http://nodejs.cn/)下载Node.js安装，建议下载大版本号为12的Node.js更方便，我这里用的是[12.21.0](https://npm.taobao.org/mirrors/node/v12.21.0/)**（补充：新的资料表示低于14版本就可以正常使用了，高于14版本也可以正常使用但是会有一些无关紧要的输出）**，大家可以根据自己的操作系统进行下载。

至于安装相信不用我多说了，也不用配置环境变量，检查安装只需要打开cmd输入：

```cmd
 npm version
```

就可以了，我这边会显示这个：，你们应该也大同小异

```cmd
{
  npm: '7.5.4',
  node: '12.21.0',
  v8: '7.8.279.23-node.45',
  uv: '1.40.0',
  zlib: '1.2.11',
  brotli: '1.0.9',
  ares: '1.16.1',
  modules: '72',
  nghttp2: '1.41.0',
  napi: '7',
  llhttp: '2.1.3',
  http_parser: '2.9.4',
  openssl: '1.1.1j',
  cldr: '37.0',
  icu: '67.1',
  tz: '2019c',
  unicode: '13.0'
}
```

## 2.3 Git 安装

前往[这里](https://git-scm.com/)下载并安装 Git，什么都不需要更改，然后输入

```cmd
 git version
```

应该会显示

```cmd
 git version 2.30.1.windows.1
```

会类似文本说明安装成功。

## 2.4 安装 Hexo

本文章提供两种安装方式（分别为 Npm 和 Yarn），建议新手使用 Npm 较为熟练的使用 Yarn 。

### 2.4.1 Npm

在终端中输入：

```cmd
 npm install -g hexo-cli 
```

然后等待即可。

### 2.4.2 Yarn

#### 2.4.2.1 安装 Yarn

前往[这个网页](https://classic.yarnpkg.com/latest.msi)下载 Windows 安装程序进行安装是最简单的方法。

完成后输入

```cmd
 yarn version
```

输出这个说明成功：

```cmd
 yarn version v1.22.5
```

#### 2.4.2.2 安装 Hexo

安装 Yarn 之后输入

```cmd
 yarn global add hexo-cli
```

即可安装 Hexo

# 3 基本

## 3.1 初始化

用 cd 命令进入一个事先准备好的目录（不会自行搜索）

输入：

```cmd
 hexo init
```

这时候会看到如下输出（理应基本相似）：

```cmd
INFO  Cloning hexo-starter https://github.com/hexojs/hexo-starter.git
[32mINFO [39m Install dependencies
INFO  Start blogging with Hexo!
```

基本内容应该相似，但是由于我这边用的是 Yarn，所以使用 Npm 安装的可能会略有不同。