---
title: 如何列出当前条目的所有字段并展示？
---


```
<div style="column-count:3;">
<$list filter='[<currentTiddler>fields:exclude[text title created modified tags creator modifier type revision bag url]]' variable=fld emptyMessage='<tr><td>no fields</td></tr>'>

<$list filter="[subfilter<fld>]" variable=fieldname>
<$list filter="[all[current]get<fieldname>]" variable=field-value>

;<<fieldname>>
:<<field-value>>

</$list>
</$list>
</$list>
</div>
```


上面代码中列出了当前条目的所有字段，除了排除的`text title created modified tags creator modifier type revision bag url`字段。同时用术语定义的方式和分成列的形式展示。

这是一个理解筛选器绝好的例子，也是筛选器嵌套使用的好例子。用到了[fields筛选器](https://bramchen.github.io/tw5-docs/zh-Hans/#fields%20Operator)。