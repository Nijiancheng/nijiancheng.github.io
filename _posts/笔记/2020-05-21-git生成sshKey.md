---
layout: blog
istop: false
title: "git 生成sshKey"
background-image:
date: 2020-05-21
category: 笔记
tags: git
---



直接右键打开 git Bash Here
移动到 ssh文件下: 
​	cd ~/.ssh 
如果提示没有该文件 "No such file or directory"可以手动创建  
​	mkdir ~/.ssh
配置全局name和email 
​	git config --global user.name "你的用户名"
​	git config --global user.email "你的公司或个人邮箱"
生成key
​	ssh-keygen -t rsa -C "你公司或个人邮箱"
得到两个文件: id_rsa 和 id_rsa.pub



进入~/.ssh文件内 cd ~/.ssh

查看  key cat id_rsa.pub