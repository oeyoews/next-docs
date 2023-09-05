---
title: HTML与文件夹的转换
---

如果你想要换种方式使用，比将HTML文件变成文件夹然后用tidgi打开，可以使用nodejs搭配一条命令完成转换。或者在tidgi太记中你可以直接导入wiki.html。


需要环境：NodeJS的安装与NodeJS版TiddlyWiki的安装。

1. 安装nvm（nodejs版本管理器）在链接：<https://github.com/coreybutler/nvm-windows/releases>  下载nvm-setup.zip，安装。
1. 打开命令行或者powershell输入：`nvm install lts` 安装最新的nodejs长期支持版。
1. 安装nodejs版TiddlyWiki，在命令行中输入：`npm install -g tiddlywiki` 等待安装成功


TiddlyWiki单文件转文件夹命令：

```sh
tiddlywiki  --load  ./mywiki.html(你的wiki文件)  --savewikifolder  ./mywikifolder(你的wiki文件夹)
```

TiddlyWiki文件夹转单文件命令:

使用Version v0.8.0-prerelease9最新版的TidGi，将wiki文件夹添加到太记中，然后使用太记顶部的Wiki菜单栏中的“导出整个Wiki为HTML存入文件夹”功能，快速实现转换。

```sh
tiddlywiki  ./mywikifolder(你的wiki文件夹)  --rendertiddler  '$:/core/save/all'  mywiki.html(你的wiki文件)  text/plain
```
