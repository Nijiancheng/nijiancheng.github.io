---
layout: blog
istop: true
title: "vue使用axios发送post请求时的坑及解决原理"
background-image:
date: 2019-09-21
category: 笔记
tags: vue axios  post 
---

# vue使用axios发送post请求时的坑及解决原理



*前言：在做项目的时候正好同事碰到了这个问题，问为什么用axios在发送请求的时候没有成功，请求不到数据，反而是报错了，下图就是报错请求本尊*

![img](https://img2018.cnblogs.com/blog/1141519/201809/1141519-20180920173422389-1463878524.jpg)

vue里代码如下：

```
   this.$http.post('/getMatterList.do',{"matterIds":"1,2,3"})
     .then((res)=>{
        console.log(res);
   })
```

乍一看，没毛病啊，请求不就是这么发的吗，axios官方文档都这么示范的呢，还能有错？我们再来仔细看下浏览器里发出去的请求

![img](https://img2018.cnblogs.com/blog/1141519/201809/1141519-20180920173444616-975473379.jpg)

有没有发现什么蹊跷，传送参数的形式不是我们熟悉的form-data，而是Request Payload。莫慌，其实我们只要做两步设置就可以解决了

- 用Qs.stringify()将对象序列化成URL的形式，Qs是axios里面自带的，所以直接引入就可以了
- 设置请求头里的'Content-Type'为'application/x-www-form-urlencoded'

```
   import Qs from 'qs'
   var data = Qs.stringify({"matterIds":"1,2,3"});
   this.$http.post('/getMatterList.do',data, {headers:{'Content-Type':'application/x-www-form-urlencoded'}}).then((res)=>{
        console.log(res)
   })
```

改完之后再来看下，妥妥的了

![img](https://img2018.cnblogs.com/blog/1141519/201809/1141519-20180920173457145-1990500516.png)

问题是解决了，但是为什么呢？查阅一番资料之后，我又回来啦

HTTP请求中的get请求和post请求参数的存放位置是不一样的，get请求的参数以*键值对*的方式跟在url后面的，而post请求的参数是以*键值对*的方式在请求体里的

- get请求

![img](https://img2018.cnblogs.com/blog/1141519/201809/1141519-20180920173534694-649580611.jpg)

- post请求

![img](https://img2018.cnblogs.com/blog/1141519/201809/1141519-20180920173519178-560688010.jpg)

为何要设置请求头里的'Content-Type'：

> 我们使用不同请求方式时，参数的传输方式是不一样的，但是服务端在取我们接口的请求参数时，用的方法其实却是一样的，都是使用request.getParameter(key)来获取，其实是因为tomcat在中间会对请求参数进行解析处理，处理完把解析出来的表单参数放在request parameter map中，所以后端就可以通过request.getParameter(key)来统一获取数据，而tomcat解析的时候是怎么知道当前的请求是post请求的呢，就是通过'contentType'，当'contentType'为"application/x-www-form-urlencoded",它才会去读取请求体数据。

为何要用Qs.stringify()将对象序列化成URL的形式：

> 在最开始的时候我们说了，post请求参数是以键值对的形式存在请求体里，用Qs.stringify()就是把传入的对象转换为键值对。

最后在vue里用axios的时候，针对post请求的问题可以做一个全局的设置，避免每个请求都要设置一遍太麻烦



转载自：https://www.cnblogs.com/Ivy-s/p/8353356.html