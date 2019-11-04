---
layout: blog
istop: false
title: "ubuntu下navicat试用到期解决办法"
background-image:
date: 2019-09-21
category: 笔记
tags: ubuntu navicat 试用到期
---

### ubuntu下navicat试用到期解决办法

直接删除 /home(有的可能在/root下)目录下的  .navicat文件夹（此文件夹隐藏），如果你是64位，文件夹名称可能为 .navicat64。

`cd /root`

`ls -al`

`rm -rf .navcat`

`rm -rf .navcat64` 64位机

接下来重新启动navicat就可以了，它会自动重新安装一遍，并且试用期重新计时。

此上做法为学习交流使用。正常使用，请购买正版