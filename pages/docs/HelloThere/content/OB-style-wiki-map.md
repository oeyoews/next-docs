---
title: Ob风格的wiki地图
---

【卡片集】

* Author：linonetwo，WhiteFall，[Peter Hajas](https://github.com/peterhajas)
* 描述：Ob风格的wiki地图。需要安装Gk0Wk/echarts插件。插件版本>=v0.2.2 。
* 使用方法：根据下列提示创建并设置条目。来源：<https://github.com/tiddly-gittly/tw-echarts/discussions/65> 。


```
条目标题：BrainMap
依赖插件：Gk0Wk/echarts
条目类型：默认TiddlyWiki5
```

```
<$echarts
  $tiddler="$:/plugins/Gk0Wk/echarts/addons/BrainMap"
  $height="500px"
  dblclick="(params, parentWidget) => { parentWidget.dispatchEvent({ type: 'tm-navigate', navigateTo: params.data.name }) }"
/>
```
