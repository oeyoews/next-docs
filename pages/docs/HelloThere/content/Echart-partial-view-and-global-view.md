---
title: Echart局部视图与全局视图
---

# TheBrian的局部视图与全局视图（与文件夹功能联动）

## 全局视图

<<thumbnail-right link:"TheBrian视图1.png" image:"TheBrian视图1.png" caption:"全局视图缩略图">>
> 加【sort参数】的文件夹功能优势是可以用数字作为前置或者后缀对文件夹进行排序，然后可以与echart绑定，把目录作为中心元素，成为全局视图。


* 全局视图可以通过绑定目录宏创建的条目，然后填写参数。
* focussedTiddler 指定图的中央节点为目录条目的条目名称。
* levels 指定图向外展开几级。

[img[TheBrian视图2.png]]

### 目录功能的条目

[img[TheBrian视图3.png]]

## 局部视图正常填写

[img[TheBrian视图4.png]]


TheBrain 各参数的用法 （来自林一二的QQ频道）：

"""
参数：focussedTiddler 是图的中央节点
参数：levels 指定图向外展开几级
参数：graphTitle 指定右下角显示的标题
参数：aliasField 用于指定展示为节点标题的字段，例如 caption
参数：excludeFilter 用于排除部分节点
"""
