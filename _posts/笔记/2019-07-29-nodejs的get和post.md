---
layout: blog
istop: true
title: "nodejs的get和post "
background-image: "/style/image/background.jpeg"
date: 2019-07-29
category: 笔记
tags: get post
---

## nodejs:

GET
GET 请求的参数在 URL 中.
原生 node 中,要想得到 get 参数,需要借助于 url 模块来识别参数字符串.
在 Express 中，不需要使用 url 模块了.可以直接使用`req.query`对象得到 GET 参数

POST
GET 请求的参数是隐蔽传参(在请求体中).
POST 请求在 Express 中不能直接获得,必须使用`body-parser`模块.使用后,将可以用 req.body 得到参数.
但是如果表单中含有文件上传,那么还是需要使用`formidable`模块.

```js
//导入post数据处理组件
var bodyParser = require("body-parser");

//  解析 post数据
app.use(bodyParser.urlencoded({ extended: false }));

//导入上传下载组件
var formidable = require("formidable");
//创建formidable对象
var form = new formidable.IncomingForm();
form.uploadDir = "./static/uploads";
```
