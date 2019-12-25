基于SpringBoot的微信点餐系统

* 项目整体介绍。[http://www.sqmax.top/springboot-project/](http://www.sqmax.top/springboot-project/) 
* 项目中涉及的知识细节及难点以博客的形式整理在Wiki里。[Wiki](https://github.com/sqmax/springboot-project/wiki)

## 运行环境：        
1. MySQL。可以下载这个在线安装器：[https://dev.mysql.com/downloads/windows/installer/8.0.html](https://dev.mysql.com/downloads/windows/installer/8.0.html)，安装MySQL社区版。
2. Redis。下载地址：[https://github.com/servicestack/redis-windows/tree/master/downloads](https://github.com/servicestack/redis-windows/tree/master/downloads)，下载最新版redis-latest.zip，解压即可。可以在解压后的根目录下看到redis-server.exe文件，双击即可启动redis服务器。
3. Nginx。下载地址：[http://nginx.org/en/download.html](http://nginx.org/en/download.html)。下载的zip压缩包，解压后根目录下有nginx.exe文件，双击即可启动nginx服务器。
4. IDEA。下载地址：[https://www.jetbrains.com/idea/download/#section=windows](https://www.jetbrains.com/idea/download/#section=windows)
4. JDK1.8+、maven、IDEA。

>注：IDEA不要下载Community版，下载Ultimate版。
MySQL数据库我用的是5.7.21的版本，本项目的建表语句好像不兼容5.6的版本，建议也装5.7以上的版本。
推荐一个比较好用的MySQL客户端：[Navicat for MySQL](https://www.navicat.com/en/download/navicat-for-mysql)。
Redis客户端图形界面：[Redis Desktop Manager](https://redisdesktop.com/download)。Maven远程仓库最好改为阿里云仓库，网上有介绍修改方式，很简单。

## 运行方式：        
1. 使用命令`git clone https://github.com/sqmax/springboot-project.git`将项目克隆到本地。
2. 将项目导入IDEA。在IDEA里，File->open...，然后选择项目文件夹（springboot-project）。如果是初次使用spring boot，这个过程可能会有点久，需要下载许多依赖的jar包。
4. 为IDEA安装lombok插件。在IDEA里，File->Settings...->Plugin，搜索lombok，安装。项目wiki介绍日志时有提到为什么安装这个插件。
3. 项目的配置文件在resources目录下，application.yml文件。修改MySQL数据库连接信息。我的数据库账号密码分别为root，123456，改为你的即可。
4. 在MySQL数据库终端运行建表语句的sql脚本（或者使用刚下载的Navicat for MySQL图形化工具），本项目的建表语句为项目根路径下的sqmax.sql
5. 启动redis。在刚才解压的Redis根目录下，双击redis-server.exe即可运行redis服务。
6. 最后就可以启动项目了。在IDEA里以Spring Boot的方式运行SellApplication这个主类。可以看到这和我们传统的web项目启动的方式不一样，我们没有配置tomcat等之类的服务器，因为Spring Boot已将服务器引入起步依赖中了。
7. 经过以上步骤，我们的项目应该已经可以启动起来了。访问：`http://127.0.0.1:8080/sell/seller/product/list`，即可来到我们的卖家端的商家管理系统界面。效果如下：

![](https://i.postimg.cc/ZnsmMkWM/PC.png)

