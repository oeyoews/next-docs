---
title: 插件更新后重启又要更新
---

先记住插件对应的名字，然后在太记里右键工作区图标-打开Wiki文件夹，在这个文件夹的 tiddlers 文件夹里，就是你所有的条目和插件了。

此时搜一下更新失败的插件，看看它是否有一个同名但以 meta 为结尾的文件，用文本编辑器打开这个文件，看看是不是里面的版本号还是旧的，没有跟随插件 JSON 文件一起更新。如果是这样，可以先删掉这个 meta 文件，然后重启太记/重启服务试试。有些插件包含了js文件，会影响启动，比如tw-react插件，同样也是删除对应的meta文件后再次启动太记。

这样应该就修好了。

目前这是一个玄学问题，有的插件会出现这样的问题，而有的插件不会出现这样的问题。也有的在这个wiki里会有，而在另一个wiki里可能就没有了。所以只好先记录可能会有问题的插件名称。删除meta文件不影响插件使用。

* `$:/plugins/linonetwo/tw-react`
* `$:/plugins/Gk0Wk/echarts`
* `$:/plugins/Gk0Wk/TW5-CodeMirror-Enhanced`
* `$:/plugins/linonetwo/github-external-image`
* `$:/plugins/linonetwo/zx-script`
* `$__plugins_Gk0Wk_focused-tiddler.json.meta`
