---
title: 返回默认版面
---

通过把 `$:/layout` 系统状态条目的内容置空，就能返回默认版面了。


```
<$action-setfield $tiddler="$:/layout" text=""/>
```

包装成按钮的效果详见[Github上的PR](https://github.com/Jermolene/TiddlyWiki5/pull/7197/commits/2852d849dd125dcaa9412c059ca1b802c758d7c4#diff-7ded7e93c04fc75d42148f2068baaf7a51a6d76c4bd48741c8a30e92c74a4755)

```
title: reset-layout
tags: $:/tags/PageControls
caption: {{$:/core/images/reset-layout-button}} {{$:/language/Buttons/ResetLayout/Caption}}
description: {{$:/language/Buttons/ResetLayout/Hint}}

\whitespace trim
<$button tooltip={{$:/language/Buttons/ResetLayout/Hint}} aria-label={{$:/language/Buttons/ResetLayout/Caption}} class=<<tv-config-toolbar-class>>>
	<$action-setfield $tiddler="$:/layout" text=""/>
	<$list filter="[<tv-config-toolbar-icons>match[yes]]">
		{{$:/core/images/reset-layout-button}}
	</$list>
	<$list filter="[<tv-config-toolbar-text>match[yes]]">
		<span class="tc-btn-text"><$text text={{$:/language/Buttons/ResetLayout/Caption}}/></span>
	</$list>
</$button>
```