---
title: Get Status Error_ XMLHttpRequest
---

会有下面的报错提示`Get Status Error: XMLHttpRequest 错误代码: 404`和`简要条目清单提取错误: XMLHttpRequest 错误代码: 404`以及类似的`syncer-browser-tiddlyweb - 2023年03月19日 10:07`，显示为tiddlyweb插件出了问题。

原因：可能是在发布HTML的时候，没有禁用掉nodejs保存用的tiddlyweb插件吧。

禁用tiddlyweb插件再git推上去，就可以了。

再然后需要把`$:/config/Plugins/Disabled/$:/plugins/tiddlywiki/tiddlyweb`文件删除。然后移除太记里的tiddlywiki，但不要删除文件夹。不然就没了。再重新添加一下文件夹，导入本地wiki。不然会一直处于单文件版本。

上面的操作还不能解决的话，就新建一个空wiki，把`tiddlywiki.info`文件里的内容复制，然后复制到出问题的wiki中的`tiddlywiki.info`里去，替换原有的文件。也就是更新`tiddlywiki.info`这个文件。

因为太记里旧的wiki文件不会自动更新配置。一些新的配置需要手动更新。从新的模板里复制过去更新。