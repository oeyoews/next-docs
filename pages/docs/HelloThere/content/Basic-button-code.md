---
title: 基本button代码
---

# 简单的开始

看完了上面文式编程的概念，我们可以从读代码的内容，然后再理解代码。先看一个简单的代码，用来实现添加新条目，同时添加一些标签和字段内容。

<$button>
<$action-sendmessage $message="tm-new-tiddler" title=<<now "YYYY年0MM月DD日0hh:0mm:0ss">> Timeform=<<now "YYYY-0MM-0DD">> tags="学习 太微相关" IsOtherText="time" TimeNumber="30" />	
	太微相关
</$button>


```
<$button>
<$action-sendmessage $message="tm-new-tiddler" title=<<now "YYYY年0MM月DD日0hh:0mm:0ss">> Timeform=<<now "YYYY-0MM-0DD">> tags="学习 太微相关" IsOtherText="time" TimeNumber="30" />	
	太微相关
	</$button>
```

上面代码中，先是button小工具，后面接一个action动作，发送一个消息，`action-sendmessage`嘛，不就是发送消息的动作，然后这个消息是什么呢？是新建一个条目，也就是`tm-new-tiddler`，前面的tm可能是tiddlywiki messages的简写。后面就是一个新条目的意思。新建一个条目最重要的就是标题，这里的标题我用了now宏，后面接一个now宏的格式参数。后面的timeform也是如此，只是格式换了一下。再后面tags就是标签的意思。这里添加标签就是直接指定了。当然有两个或以上的标签时，需要空格区分开来。如果英文标签里有两个以上的单词时，就需要添加`[[]]`来区分开来。

ok，以上就基本上是新建一个自定义的按钮的基本操作了。当然还可以做一些优化，具体可见[如何做一个合格的按钮](https://dongrentianyu.github.io/WENAI/#%E5%A6%82%E4%BD%95%E5%81%9A%E4%B8%80%E4%B8%AA%E5%90%88%E6%A0%BC%E7%9A%84%E6%8C%89%E9%92%AE)。

现在我们要开始讲复杂的内容了。不过也是在上面的基础展开的。