---
title: 全平台软件和存储方式
---

# 使用、存储方式与全平台软件

<<alert-leftbar secondary "思维导图（左上角）：<https://www.zhixi.com/view/70759713> （因子，聚集，自由组合）" width:60%>>

<<alert info "''Notes''：TiddlyWiki非常灵活拥有：''HTML文件''与''文件夹'' 2种存储形式；''桌面浏览器''，''服务端软件''，''应用软件'' 3种使用方式。">>

<$macrocall $name="alert" type="primary" src="
**全平台软件列表：**

* Windows、macOS、Linux ：[TidGi](TidGi太记)、[Timimi](https://ibnishak.github.io/Timimi/)、[TiddlyDesktop](https://github.com/TiddlyWiki/TiddlyDesktop/releases)、[TiddlyStow](https://twpub-book.netlify.app/tiddlystow.html)、[NodeJS](https://nodejs.org/zh-cn/)

* Android：[Tiddloid](https://github.com/donmor/Tiddloid) + [WebDav_Server_Pro_1.17](https://zhuanlan.zhihu.com/p/543783107)

* IOS与IPad：Quine2、VPS（虚拟专用服务器）

* VPS与服务器：[NodeJS](https://nodejs.org/zh-cn/)、WebDav、[TiddlyHost](https://tiddlyhost.com)

* [GitHub桌面版](https://desktop.github.com/)、[Git分布式版本控制系统](https://git-scm.com/)、[TidGi默认Wiki知识库模板（GitHub）](https://github.com/tiddly-gittly/Tiddlywiki-NodeJS-Github-Template)
" class="bg-transparent"/>




---
NodeJS:[如何启动一个NodeJS的TiddlyWiki项目](#%E5%A6%82%E4%BD%95%E5%90%AF%E5%8A%A8%E4%B8%80%E4%B8%AANodeJS%E7%9A%84TiddlyWiki%E9%A1%B9%E7%9B%AE)

WebDav: WsgiDAV(python通过PIP安装或者MSI安装程序)，Rclone，IIS WebDav

[HTML与文件夹的转换](#HTML%E4%B8%8E%E6%96%87%E4%BB%B6%E5%A4%B9%E7%9A%84%E8%BD%AC%E6%8D%A2):tiddlywiki单文件可以解压后提供给nodejs，TidGi使用
<br><br>

# 安卓移动服务器

将手机作为知识库存储位置吧。  

安卓方案：Tiddloid + WebDav_Server_Pro_1.17

WebDav_Server_Pro_1.17安装使用简单，支持太微文档列表、支持为太微在桌面创建快捷方式、支持备份、创建副本，支持其它设备通过浏览器、文件资源管理器和局域网访问，你可以和Tiddloid配合使用，解锁高级功能。

webdav服务器、系统与浏览器API、nodejs运行环境。移动服务器、桌面服务器、网站服务器、云盘与同步

<br><br>

# Termux与NodeJS


* Termux的bash.bashrc文件位置：$PREFIX/etc/bash.bashrc
* Termux中手机内部存储位置：$HOME/storage/shared   
* [在桌面端访问Termux终端](#%E5%9C%A8%E6%A1%8C%E9%9D%A2%E7%AB%AF%E8%AE%BF%E9%97%AETermux%E7%BB%88%E7%AB%AF) 
* 在Android中配置NodeJS：[TiddlyWiki-XP Serving TW5 from Android](https://keatonlao.github.io/tiddlywiki-xp/#Serving%20TW5%20from%20Android)
<br><br>


# HTML与文件夹的转换

{{HTML与文件夹的转换}}
