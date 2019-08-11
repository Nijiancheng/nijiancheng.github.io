---
layout: post
title:  "2019-07-29-nodejs的get和post"
categories: Note
tags: Note
description: 2019-07-29-nodejs的get和post.
---

#### nodejs:

GET
GET请求的参数在URL中.
原生node中,要想得到get参数,需要借助于url模块来识别参数字符串.
在Express中，不需要使用url模块了.可以直接使用`req.query`对象得到GET参数

POST
GET请求的参数是隐蔽传参(在请求体中).
POST请求在Express中不能直接获得,必须使用`body-parser`模块.使用后,将可以用req.body得到参数.
但是如果表单中含有文件上传,那么还是需要使用`formidable`模块.

```js
//导入post数据处理组件
var bodyParser = require('body-parser');

//  解析 post数据
app.use(bodyParser.urlencoded({ extended: false }));

//导入上传下载组件
var formidable = require('formidable');
//创建formidable对象
var form = new formidable.IncomingForm();
form.uploadDir = "./static/uploads";
```



