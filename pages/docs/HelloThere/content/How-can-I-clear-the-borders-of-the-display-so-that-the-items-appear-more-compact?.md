---
title: 如何清除展示的边框，让条目显得更紧凑？
---

原始的如下面代码所示，边框挺大的，对于偏小的电脑来说，就有点浪费空间了。

```
.tc-tiddler-frame {
    padding: 28px 42px 42px 42px;
    padding-top: 28px;
    padding-right: 42px;
    padding-bottom: 42px;
    padding-left: 42px;
		}
```

解决办法也很容易，新建一个条目，条目名称无所谓，标签是`$:/tags/Stylesheet`，正文内容跟上面一样，不过需要把数值修改一下。我的模板如下。具体数值可以自行调整的。


```
.tc-tiddler-frame {
    padding: 5px 10px 5px 20px;
    padding-top: 5px;
    padding-right: 10px;
    padding-bottom: 5px;
    padding-left: 20px;
		}
```

官方有一个`$:/themes/tiddlywiki/seamless`插件。也是移除边框的，可以试试。
