---
title: 在筛选器中使用宏或变量
---

根据[筛选器参数-中文教程](https://bramchen.github.io/tw5-docs/zh-Hans/#Filter%20Parameter)，筛选器操作符的参数可以是：

软式 - 变量：`<like this>` 该参数是变量当前的值，角括号之间的文本为参数名称。

* `[xxx]`就是指"xxx"字符串
* `<xxx>`是指xxx变量
* `{xxx}`是指xxx条目的text字段
* `{xxx!!yyy}`是指xxx条目的yyy字段
* `{!!yyy}`是指当前条目的yyy字段
* `[<xxx>!match[]]`是判断当前变量存不存在

简单来说，就是把原版宏两个的尖括号，变成一个就好。

## 例子

### 通过筛选器获得有固定开头、日期为结尾的条目名

```
[<now "YYYY-MM-DD">] +[addprefix[$:/state/tw-mobile-sync/server/]]
```

其中用 `[<now "YYYY-MM-DD">]` 这个方式在筛选器中使用了日期宏，原版的宏写法为 `<<now "YYYY-MM-DD">>` 。