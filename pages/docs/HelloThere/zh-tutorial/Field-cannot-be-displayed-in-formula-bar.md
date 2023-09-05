---
title: 字段无法显示在编辑栏中
---

最近钓鱼插件大更新了。题目设置在caption中。然后制作了一个更方便的编辑模板，并把caption字段隐藏起来了。

但平时添加条目用到caption字段时，隐藏起来编辑就很不方便了。所以我们需要新建一个条目，标题填`$:/config/EditTemplateFields/Visibility/caption`，里面的内容填`yes`。

类似的，如果其他字段也无法正常显示了，一般也是因为插件隐藏起来了，所以只需要建一个条目，标题写`$:/config/EditTemplateFields/Visibility/xxx`，内容填`yes`。这样xxx字段就会显示了。如果不想显示，那就填no