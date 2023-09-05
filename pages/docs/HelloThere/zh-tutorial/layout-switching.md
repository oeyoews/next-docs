---
title: 版面切换
---

## 简介

### 常用视图

白板：<https://tw-cpl.netlify.app/#linonetwo%2Ftw-whiteboard>

<img src="https://pic1.zhimg.com/80/v2-73dfc44959d9f793b6746910ea08ed58_720w.webp">

日历：<https://tw-cpl.netlify.app/#Plugin_202212022054901>

<img src="https://pic2.zhimg.com/80/v2-bc2f1bea0dd0016a212bf004782c4431_720w.webp">

（内容为林一二新冠一周病情日记）

默认故事流

<img src="https://pic2.zhimg.com/80/v2-13aa858ca7467849ce71f581546209f1_720w.webp">

### 视图切换

可以用页面工具栏里的 Layout switcher 来打开视图列表切换

<img src="https://pic1.zhimg.com/80/v2-2cd7d142e8c902e2acf1dcac0523563c_720w.webp">

<img src="https://pic2.zhimg.com/80/v2-a257f0df025ea661ba60949ec009c9c5_720w.webp">

有的视图插件也向页面工具栏提供了新按钮，例如这个一键切换到日历的按钮

<img src="https://pic2.zhimg.com/80/v2-993ca6a4b8a0acc2232518956486a67d_720w.webp">

## 框架部分

太微大部分界面是用维基文本文式编程写的，可以通过 message 等机制调用 JS 侧的能力，JS 侧也可以通过 `$tw.wiki.`makeTranscludeWidget 等方式取到笔记里的内容。

设计上维基文本是希望成为低代码，不过对普通人来说用起来和 HTML 差不多，不看文档学也不会用，下面简单介绍一下。

页面工具栏上的按钮是这样的：

```
title: $:/core/ui/Buttons/layout
tags: $:/tags/PageControls

<$button tooltip={{$:/language/Buttons/LayoutSwitcher/Hint}}>
  <$action-sendmessage $message="tm-show-switcher" switch="layout"/>
</$button>
```

在一个启动项脚本里，注册了暴露给维基文本的可用消息 `tm-show-switcher`（类似 JSB）

JS 侧收到这个消息后，会弹一个框出来，里面展示笔记条目 `$:/core/ui/SwitcherModal` 的内容

并带上 `{ switch: "layout" }` 作为维基文本变量，传给维基文本侧

```
exports.name = "rootwidget";
exports.platforms = ["browser"];
exports.after = ["startup"];
exports.before = ["story"];
exports.synchronous = true;

// ...

  $tw.rootWidget.addEventListener("tm-show-switcher",function(event) {
    $tw.modal.display("$:/core/ui/SwitcherModal",{variables: event.paramObject, event: event});
  });
```

在维基文本里，可以通过 `<varName>` 的方式把上下文中的变量拼入文本里，总之下面的维基文本拼出了 `$:/config/SwitcherTargets/layout`，取出对应的值 `$:/snippets/LayoutSwitcher`，然后嵌入了这条笔记。

```
title: $:/core/ui/SwitcherModal
subtitle: <$text text={{{[<switch>lookup[$:/language/Switcher/Subtitle/]]}}}/>
class: tc-modal-centered
mask-closable: yes

<$tiddler tiddler={{{ [<switch>lookup[$:/config/SwitcherTargets/] ]}}}>

<$transclude/>

</$tiddler>
```

```
title: $:/config/SwitcherTargets/

layout: $:/snippets/LayoutSwitcher
language: $:/snippets/languageswitcher
palette: $:/core/ui/ControlPanel/Palette
theme: $:/core/ui/ControlPanel/Theme
```

这条笔记是切换视图的弹框，通过 `<$list>` 微件，筛选出带有标签 `$:/tags/Layout` 的笔记，把它们作为链接列在列表里，点了就会把点击的视图笔记的 title 设置到 `$:/layout` 笔记的内容里。

```
title: $:/snippets/LayoutSwitcher

<$linkcatcher to="$:/layout">
  <$list
    filter="[all[tiddlers+shadows]tag[$:/tags/Layout]] +[!is[draft]sort[name]]"
  >
    <$link to={{!!title}}>
      <strong><$transclude field="name"/> </strong><$transclude field="description"/>
    </$link>
  </$list>
</$linkcatcher>
```

最终，太微在根笔记 `$:/core/ui/RootTemplate` 里取出 `$:/layout` 这个笔记的内容，也就是当前打开的视图笔记的 title。

然后就会把我们所选的视图笔记嵌入进来，作为 `$:/core/ui/RootTemplate` 的实际内容。

```
title: $:/core/ui/RootTemplate

<$transclude
  tiddler={{{ [{$:/layout}has[text]] ~[[$:/core/ui/PageTemplate]] }}}
  mode="inline"
/>
```

在 JS 侧挂载这个笔记到 dom 上，类似于 react-dom 挂载 react 组件到 dom 上：

```
const pageWidgetNode = $tw.wiki.makeTranscludeWidget('$:/core/ui/RootTemplate', {
  parentWidget: $tw.rootWidget,
});

const pageContainer = document.createElement('div');
document.body.insertBefore(pageContainer, document.body.firstChild);
$tw.pageWidgetNode.render(pageContainer);
```

## 插件部分

插件就是打包的笔记。插件提供的新视图一般用来展示一个微件。

例如先创建一个日历微件的 JS 侧代码

src/calendar-widget/widget.ts

```
import { Calendar } from '@fullcalendar/core';
import type { Widget as IWidget } from 'tiddlywiki';
import './widget.css';

const Widget = (require('$:/core/modules/widgets/widget.js') as { widget: typeof IWidget }).widget;

class CalendarWidget extends Widget {
  /**
   * Lifecycle method: Render this widget into the DOM
   */
  render(parent: Node, _nextSibling: Node): void {
    this.#calendar = new Calendar(this.#mountElement, { ...settings });
    this.#calendar?.render();
    parent.appendChild(this.#containerElement);
  }
}

exports.widget = CalendarWidget;
```

然后通过元信息文件，保存这个笔记的标题、标签、类型等元信息

src/calendar-widget/widget.js.meta

```
creator: LinOnetwo
title: $:/plugins/linonetwo/tw-calendar/calendar-widget/widget.js
type: application/javascript
module-type: widget
hide-body: yes
```

之后就可以在维基文本侧使用定义的微件，用类似 XML 的语法使用它 `<$calendar height="100vh" />`

```
title: $:/plugins/linonetwo/tw-calendar/tiddlywiki-ui/PageLayout/CalendarLayout
name: Calendar
description: view tiddlers in agenda or calendar by their date related fields
tags: $:/tags/Layout

\import [[$:/core/ui/PageMacros]] [all[shadows+tiddlers]tag[$:/tags/Macro]!has[draft.of]]

<$navigator story="$:/StoryList" history="$:/HistoryList" openLinkFromInsideRiver={{$:/config/Navigation/openLinkFromInsideRiver}} openLinkFromOutsideRiver={{$:/config/Navigation/openLinkFromOutsideRiver}} relinkOnRename={{$:/config/RelinkOnRename}}>

    <main class="tw-calendar-layout-main-area">
      <$calendar height="100vh" />
    </main>

</$navigator>
```

通过给这个笔记加上 `tags: $:/tags/Layout` 这个标签，它就会被太微的框架部分使用到，展示在可用视图列表里

并在它的 title 作为 `$:/layout` 这个笔记的内容时，替换掉默认的故事流视图，全屏展示这个新的视图。
