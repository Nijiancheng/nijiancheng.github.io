---
layout: post
title:  "2019-07-29-nodejs 的ejs 模板"
categories: Note
tags: Note
description: 2019-07-29-nodejs 的ejs 模板.
---

### ejs:

###### ejs模版

node中有很多模板 ejs 只是其中一个
http://www.embeddedjs.com/        #官网
https://www.npmjs.com/package/ejs #npm上的ejs包
ejs是Embedded JavaScript templates的简称,意思是嵌入式JavaScript模板.node中的后台模版.

http://www.jianshu.com/p/67dda091fc68

使用: 直接npm 安装即可npm insatll ejs --save

使用淘宝 NPM 镜像
大家都知道国内直接使用 npm 的官方镜像是非常慢的，这里推荐使用淘宝 NPM 镜像。
淘宝 NPM 镜像是一个完整 npmjs.org 镜像，你可以用此代替官方版本(只读)，同步频率目前为 10分钟 一次以保证尽量与官方服务同步。
你可以使用淘宝定制的 cnpm (gzip 压缩支持) 命令行工具代替默认的 npm:
$ npm install -g cnpm --registry=https://registry.npm.taobao.org
这样就可以使用 cnpm 命令来安装模块了：
$ cnpm install [name]

###### ejs使用：

​	在app.js添加:

1. app.set('views',__dirname+'views');//设置模板引擎的目录
2. app.set('views engine','ejs');//设置模板引擎是什么

index.js向模板传递数据（以json格式）

```js
 router.get('/',(,req,res) => {
 		res.render('index',{ name:'lichangtao'});
   		//也可以先定义对象，再传入（可以是一个或多个）
		let obj = {};
	 	res.render('index',{ data1:obj1,data2:obj2,... });
 });
```

###### 模板文件index.ejs接收数据：   　 

　<%= json数据名 %> //不解析HTML代码，直接显示

​	 <%- json数据名 %> //解析HTML代码

