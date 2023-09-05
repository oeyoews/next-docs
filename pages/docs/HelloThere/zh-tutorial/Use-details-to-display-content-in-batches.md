---
title: 批量使用details展示内容
---


```
<$list filter="[tag[Widgets]]">

<$macrocall $name="details" label={{!!title}} src={{!!text}} />

</$list>
```

上面的代码用到了设拉子插件，但不用这个插件也是可以实现的，就是自己写details标签的语法。然后里面的内容也是用`{{!!title}}`来嵌入实现的。当然上面的语法还是用5.3.0版本之前的，后面的版本也能用，但更推荐在5.3.0版本之后使用下面的代码。


```
<$list filter="[tag[Widgets]]">

<$transclude $variable="details" label={{!!title}} src={{!!text}} />

</$list>
```

效果是一样的，可能后者性能还更快一点。里面筛选器部分就自己修改成需要筛选的内容了。设拉子的插件是可以选择样式的，也自己选择就行了