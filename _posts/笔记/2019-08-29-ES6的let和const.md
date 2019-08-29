---
layout: blog
istop: false
title: "ES6的let和const"
background-image:
date: 2019-08-29
category: 笔记
tags: ES6 let const
---

## ES6

### let

#### let关键字的用法规范：

- 声明变量
- let声明的变量不能重复声明
- 不存在变量提升， 临时性死区    ？
- 声明不会提前

```js
function fu(){
    console.log(username);
    let username = "小丽丽";
}
fu();
```

控制台打印会报错：

![](/home/github/nijiancheng.github.io.cope/style/images/2019-08-29 11-28-30-let声明.png)

#### 块级作用域:

- 代替闭包的一些功能

```html
<ul id="myList">
		<li>0Lorem ipsum dolor sit amet.</li>
		<li>1Lorem ipsum dolor sit amet.</li>
		<li>2Lorem ipsum dolor sit amet.</li>
		<li>3Lorem ipsum dolor sit amet.</li>
	</ul>

	<script>
		let lis = document.querySelectorAll("#myList li");

		for (let i = 0; i < lis.length; i ++) {
			lis[i].onclick = function(){
				console.log(i);
			}
		}
	</script>
```

点击会打印对应序号，不会与其他li冲突：

![](/home/github/nijiancheng.github.io.cope/style/images/2019-08-29%2011-41-35%E7%82%B9%E5%87%BB%E6%89%93%E5%8D%B0%E5%AF%B9%E5%BA%94%E5%BA%8F%E5%8F%B7.png)

- 大括号可以产生块级作用域

块级作用域

```js
if(true){
    var a =100;
    let b = 200; //具有块级作用域
    console.log(b);
}

console.log(a);
```

输出结果：

![](/home/github/nijiancheng.github.io.cope/style/images/2019-08-29 11-49-41块级作用域.png)

### const

- 声明常量
- 常量的值一旦声明就不能更改
- const声明的常量同样存在作用域（局部作用域、块级作用域、全局作用域）

const与let作用域很是相似

### 全局作用域和顶层对象

- ES6中去掉了顶层对象的概念
- 为了向下兼容，在全局作用域中使员var声明的变量和直接声明的函数仍然是顶层对象的属性和方法。 而使用let和const声明的变量不再输入顶层对象

```js
var username ="小红";
function fu(){
    console.log("I am fu");
}

console.log(window.username);
window.fu();
let userage =100;
console.log(window.userage);
```

输出结果：

![](/home/github/nijiancheng.github.io.cope/style/images/2019-08-29 12-03-32顶层对象和全局作用域.png)