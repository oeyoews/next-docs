---
title: 在宏定义里使用变量
---

参考[中文文档-宏](https://bramchen.github.io/tw5-docs/zh-Hans/#Macros)

> 在片段本身检测到的唯一标记是 `$name$`（宏参数的占位符）和 `$(name)$`（ [变量](#%E5%8F%98%E9%87%8F)的占位符）。

### 使用环境中的变量

例如官方展示按钮的这个例子：

```tw5
\define tag-styles()
background-color:$(backgroundColor)$;
fill:$(foregroundColor)$;
color:$(foregroundColor)$;
\end

\define tag-body-inner(colour,fallbackTarget,colourA,colourB,icon)
\whitespace trim
<$vars foregroundColor=<<contrastcolour target:"""$colour$""" fallbackTarget:"""$fallbackTarget$""" colourA:"""$colourA$""" colourB:"""$colourB$""">> backgroundColor="""$colour$""">

  <$button class="tc-tag-label" style=<<tag-styles>> >
 		XXX
  </$button>

</$vars>
\end
```

当场声明一个 `tag-styles` 宏，里面用 `$(backgroundColor)$` 这种方式使用变量。

这里使用`$(name)$`（ [变量](#%E5%8F%98%E9%87%8F)的占位符）

### 使用宏参数

可以看到这个变量是在下面 `tag-body-inner` 的宏定义里，通过 `<$vars backgroundColor="""$colour$"""` 放到环境里的。这里也是通过 `$colour$` 的方式使用了环境里通过参数传入的 `colour` 变量。

这里使用 `$name$`（宏参数的占位符）。

这里的三引号 `"""` 和普通的引号差不多，和变量无关，你用单个引号也行，参考[中文文档-宏调用](https://bramchen.github.io/tw5-docs/zh-Hans/#Macro%20Calls%20in%20WikiText)：

> 每个参数的值可以包裹于`'`单引号`'`、`"`双引号`"`、`"""`三重双引号`"""`或`[`双方括弧`](#%60%E5%8F%8C%E6%96%B9%E6%8B%AC%E5%BC%A7%60)`。三重双引号允许包含几乎所有的值。如果参数值未包含空格、单引号或双引号，则无须分隔符号。