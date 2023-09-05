---
title: 页面按钮筛选显示
---

我最近探索发现，一个按钮，要么在所有条目里显示，要么就不显示。不能像编辑栏里的按钮按照筛选器来显示。这可能是后续要增加的功能。

其实可以做到，主要是通过list和reveal来处理。比如所见即所得页面上的按钮，我要控制在系统条目上不显示。在图片条目上也不显示。那么就可以从下面的筛选器来排除。

```
<$list filter="[<currentTiddler>field:type[text/vnd.tiddlywiki]!prefix[$:/]] :or[<currentTiddler>!prefix[$:/]field:type[]]"> 
```

先是在当前条目里，筛选出type为常见wiki格式的，并排除标题前缀为`$:/`的，这就排除了系统条目。或者type类型没写的，也可以，但同样要排除标题前缀为`$:/`的。

上面的代码可以简化为`<$list filter="[<currentTiddler>!prefix[$:/]]"></$list>`，这个非常实用，因为很多自定义设置不需要在系统条目里展示，比如当前条目位置。