---
layout: blog
istop: false
title: "ejs模板 "
background-image: "/style/image/background.jpeg"
date: 2019-07-29
category: 笔记
tags: ejs安装和使用
---

## ejs:

### ejs 模版

node 中有很多模板 ejs 只是其中一个
http://www.embeddedjs.com/ #官网
https://www.npmjs.com/package/ejs #npm 上的 ejs 包
ejs 是 Embedded JavaScript templates 的简称,意思是嵌入式 JavaScript 模板.node 中的后台模版.

http://www.jianshu.com/p/67dda091fc68

使用: 直接 npm 安装即可 npm insatll ejs --save

使用淘宝 NPM 镜像
大家都知道国内直接使用 npm 的官方镜像是非常慢的，这里推荐使用淘宝 NPM 镜像。
淘宝 NPM 镜像是一个完整 npmjs.org 镜像，你可以用此代替官方版本(只读)，同步频率目前为 10 分钟 一次以保证尽量与官方服务同步。
你可以使用淘宝定制的 cnpm (gzip 压缩支持) 命令行工具代替默认的 npm:
$ npm install -g cnpm --registry=https://registry.npm.taobao.org
这样就可以使用 cnpm 命令来安装模块了：
$ cnpm install [name]

### ejs 使用：

​ 在 app.js 添加:

1. app.set('views',\_\_dirname+'views');//设置模板引擎的目录
2. app.set('views engine','ejs');//设置模板引擎是什么

index.js 向模板传递数据（以 json 格式）

```js
 router.get('/',(,req,res) => {
 		res.render('index',{ name:'lichangtao'});
   		//也可以先定义对象，再传入（可以是一个或多个）
		let obj = {};
	 	res.render('index',{ data1:obj1,data2:obj2,... });
 });
```

### 模板文件 index.ejs 接收数据： 　

<%= json 数据名 %> //不解析 HTML 代码，直接显示

​ <%- json 数据名 %> //解析 HTML 代码
