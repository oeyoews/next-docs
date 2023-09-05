---
title: 让导入的图片放在特定目录中
---

首先添加一个条目`$:/config/FileSystemPaths`，内容如下： 

`[!is[system]has[save-to]get[save-to]] [get[title]search-replace:g:regexp[/|\\],[_]] +[join[/]] `

然后在拖入的图片加上`save-to`字段，内容是`images`，这图片就会自动加入`images`文件夹。 

以上方法由群友@徵羽所写，只作简化处理。

上面`save-to`字段和`images`文件夹，都是可以自定义修改的。这应该是用到了太微文件系统特性。具体可看[文档介绍](https://bramchen.github.io/tw5-docs/zh-Hans/#Customising%20Tiddler%20File%20Naming)。