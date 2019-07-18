# DAY1

2019年7月17日

星期三

### 系统安装ubuntu系统

安装双操作系统

​	easyBCD 安装：

​		下载easyBCD 打开

​		选择添加新条目 

​		右侧选择iso镜像地址加载

​		加载完成重启进入ubuntu系统

​	U盘安装：（由于部分电脑启动引导是UEFI ，导致easyBCD 的功能不能使用，所以使用U盘安装）

​		 1.进入控制面板->磁盘管理->压缩磁盘获得50G空间

​	 	2.下载ubuntu iso镜像文件

​		 3.将镜像文件存入U盘

​		 4.重启电脑，选择U盘启动

​		 5.根据提示选择安装并等待

​		 6.安装完成

### liunx下的vim操作

​	 / ：搜索内容 

​	 i ：进入插入模式

​	 esc：退出当前操作

 	shift + ；：输入命令

​	 q + <Enter>： 推出vim

​	 q！+ <Enter>：强制退出

​	 w + <Enter>：保存当前内容

​	 wq + <Enter>：保存并退出

 	help + <Enter>: 查看帮助

选中后就可以用编辑命令对其进行编辑，如 
	d   删除 

​	y   复制 （默认是复制到"寄存器） 

​	p  粘贴 （默认从"寄存器取出内容粘贴）

### 安装git

​	apt-get install git

### 安装vim 

​	apt-get install vim

### 安装chromium浏览器

​	apt-cache search Chrome

​	apt-get install chromium-browser

### github操作

 	1.创建仓库 名为 username.github.io

 	2.本地拉取远程仓库

​			1.初始化`git init` 

​			2.`git config --global  user.name  'github上注册的用户名';`

​			3.`git config --global user.email '注册时候邮箱'；`

​			4.克隆远程库到本地

​				`git clone https://github.com/username/username.github.io`     username是用户自己的注册名；

 	   	5.移动到本地拉取的库文件中

​				`cd username.github.io` 

​		3.提交数据到远程github中

​			1.查看更改的文件 git status

​			7.将新建文件添加到一个存储区 git add --all （添加全部更改文件） /git add 文件名 （添加某个文件）

​			8.git commit -m "本次操作的简述"

​			9.git push -u origin master  上传到远端

