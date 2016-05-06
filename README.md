# study-JQuery
JQuery基础学习

## JQuery环境搭建（自定义JQuery）

Query从1.9开始将构建工具迁移到grunt，grunt是基于node的，因此需要安装node；

### 安装node

mac用户直接使用home-brew安装即可；至于如何安装homebrew请自行百度；
	brew install node

windows用户请自行百度；

### 安装grunt

使用npm安装，执行以下命令：
	npm install -g grunt-cli

对于mac或者linux用户需要使用管理员权限安装；

检查安装是否成功：
	grunt -v
安装成功会显示出当前安装的grunt版本，如下：
![][image-1]

### 下载JQuery

JQuery源码托管在github上，地址为：[https://github.com/jquery/jquery][1]
使用使用git桌面工具或者git命令下载JQuery源码到本地；

### 编译JQuery源码

cd到JQuery目录，直接执行命令即可：
	grunt

在Query的目录下会多出一个dist目录，该目录下有三个文件：未压缩的jquery.js，压缩的jquery.min.js和souremap(jquery.min.map需浏览器支持)；和官网提供的最终版本无任何区别；
![][image-2]

如果要使用不同版本的jqeury，执行将当前代码分支使用git切换到指定版本，再执行以上步骤即可；

### 定制JQuery

Query采用模块开发，具体模块如下：
![][image-3]

除了核心模块积极选择器不能定制之外，其他的模块都可以定制；需要不包含某个模块使用如下命令即可：
	grunt custom:-模块名

例如：
现在将编译的jquery.js中不包含ajax，只需执行以下命令编译：
			grunt custom:-ajax

多个模块使用逗号分隔，如：
		grunt custom:-ajax,-effects

### 参考

Query构建参考[https://github.com/jquery/jquery]()

[1]:	https://github.com/jquery/jquery


[image-1]:	grunt%20-v.png
[image-2]:	dist-jquery.png
[image-3]:	core.png