---
title: 太微如何显示界面
---

有一些 JS 笔记，含有元信息 `module-type: widget`，它们 exports 上的内容会被加入微件（Widget）注册表，待用。

用户日常写的笔记，进入渲染流程后，会被解析器变成抽象语法 🌲，例如一篇纯纯的文本笔记，通过 `$tw.wiki.parseText('text/vnd.tiddlywiki', input).tree` 会解析出：

```js
{type: "text", text: <string>} // a text node
```

此后将这颗语法树通过核心 API 转换成 DOM 节点：

```js
const newWidgetNode = parentWidget.makeChildWidget(parseTreeNode);
newWidgetNode.render(domNode, null);
```

这个过程中会去查表，找到相应的微件渲染器：

```js
/*\
title: $:/core/modules/widgets/text.js
type: application/javascript
module-type: widget

Text node widget

\*/
/*
Inherit from the base widget class
*/
TextNodeWidget.prototype = new Widget();
/*
Render this widget into the DOM
*/
TextNodeWidget.prototype.render = function(parent,nextSibling) {
  this.parentDomNode = parent;
  this.computeAttributes();
  this.execute();
  var text = this.getAttribute("text",this.parseTreeNode.text || "");
  text = text.replace(/\r/mg,"");
  var textNode = this.document.createTextNode(text);
  parent.insertBefore(textNode,nextSibling);
  this.domNodes.push(textNode);
};
```

执行 `render` 方法后，就完成了渲染。在用户改动文本后，会有其他生命周期方法被调用，从而刷新界面。

由于微件渲染器也是个笔记，所以说可以通过插件社区来分发，让用户按需加载。