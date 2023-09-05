---
title: 如何修改编辑器字体大小？
---

[论坛链接](https://talk.tiddlywiki.org/t/changing-editor-font-size/2596)

上面的论坛链接里说明了一般模式下修改编辑器字体大小的方式。也就是把下面的代码复制到一个新条目里，并添加`$:/tags/Stylesheet`标签。

```
.tc-edit-texteditor-body {
    font-size: 24px;
    line-height: 30px;
}
```

但notebook主题比较特殊，需要用另外的代码来修改。具体参考下面的代码。

```
.CodeMirror-lines {
  cursor: text;
  min-height: 1px;
  font-size: 34px;
  line-height: 30px;
}
```

里面font-size的数值可以自己调整。