---
title: 太微如何加载核心 API 和插件提供的 API
---

上面的 `$tw.wiki.addTiddlers` 是在最早加载的 `boot.js` 里通过 `$tw.Wiki.prototype.addTiddlers = function` 放入 `$tw` 全局变量的，而后续的其他大部分核心都是以笔记的形式加载的。

例如 `$tw.wiki.getTiddlerText` 就处在一个标题为 `$:/core/modules/wiki.js` 的笔记里：

```
/*\
title: $:/core/modules/wiki.js
type: application/javascript
module-type: wikimethod

\*/
exports.getTiddlerText = function xxx
```

它被加载到应用程序内存里之后，核心代码通过 `type` 判断这条笔记是可执行的，就这条笔记装入 `$tw.modules` 里存着，以备之后用 `$tw.modules.execute` 通过 `new Function` 的方式执行它。

又会根据 `module-type` 是 `wikimethod`，就将它里面 `exports` 上的内容附着到 `$tw.wiki` 的原型链上，以便代码的其他部分能够调用到这个函数。其它 `module-type` 则会有其它使用其 `exports` 内容的方式。