---
title: HTML与文件夹的转换
---

>需要环境：安装nodejs，在nodejs安装中TiddlyWiki软件包。

TiddlyWiki单文件转文件夹命令：


```
tiddlywiki --load ./mywiki.html --savewikifolder ./mywikifolder
```




TiddlyWiki文件夹转单文件命令：


```
tiddlywiki ./mywikifolder --rendertiddler '$:/core/save/all' mywiki.html text/plain
```




转换完成后的文件将会在mywikifolder的output文件夹中保存。

>文件夹转单文件，可以使用TidGi打开TiddlyWiki文件夹，然后安装tiddlywiki/tiddlyweb太微插件，使用它的Save snapshot for offline use功能实现。


[img[Save-snapshot--.png]]



>mywikifolder是文件夹版tiddlywiki的文件夹，mywiki.html为单文件版TiddlyWiki。

**应用场景**，可以用于TidGi-0.7.7版本的单文件太微模版的导入。