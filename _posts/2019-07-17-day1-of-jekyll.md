### DAY1

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

​			1.`git init` 初始化

​			2.`git config --global  user.name  'github上注册的用户名';`

​			3.`git config --global user.email '注册时候邮箱'；`

​			4.`git clone https://github.com/username/username.github.io`     username是用户自己的注册名；

 	   	5.`cd username.github.io` 移动到本地拉取的库中

​			6.新建文件

​			7.git add --all 将新建文件添加到一个存储区

​			8.git commit -m "本次操作的简述"

​			9.git push -u origin master  上传到远端

### jekyll 

​		`sudo apt-get install ruby-full build-essential zlib1g-dev`  安装环境要求文件

​		将环境变量写入文件配置中

​	    `echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc`

​		`echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc`

​		`echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc`

​		`source ~/.bashrc`

​		`gem install jekyll bundler` 安装jekyll

​		`jekyll new myblog` 创建一个新的jekyll网站

​		`cd myblog`  转到新目录

​		`bundle exec jekyll serve`构建站点并在本地服务器上使用

<br/>

### Thanks：

1，[Chris.com][chris-ascii-art]

2，[ASCII Generator][ascii-generator]

[chris-ascii-art]: http://www.chris.com/ascii/
[ascii-generator]: http://www.network-science.de/ascii/
[welcome-lost-in-xixia]: http://xixia.info/welcome-lost-in-xixia