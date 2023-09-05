---
title: 如何让编辑与预览同步？
---

这个有两种解决办法。一种是买个大一点的显示器，这个是比较好的，大的显示器会在各个方便都提供帮助。另一种解决办法就是修改样式。新建一个条目，把下面的代码复制过去。

```
.tc-tiddler-preview {
	overflow: scroll;
}.tc-tiddler-preview-preview {
	float: right;
	width: 100%;
	border: 1px solid #cccccc;
}.tc-tiddler-frame .tc-tiddler-preview .tc-edit-texteditor {
	width: 100%;
}.tc-tiddler-frame .tc-tiddler-preview canvas.tc-edit-bitmapeditor {
	max-width: 49%;
}
```

然后加上`$:/tags/Stylesheet`的标签，并设置编辑器的高度为固定高度。

编辑和预览两个都有滚动条可以查看。但同样也不是很方便的，所以如果只是纯文本的话，那基本上也不需要开查看模式的。