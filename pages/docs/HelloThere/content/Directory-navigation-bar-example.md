---
title: 目录导航栏实例
---

<style>
<!-- 修改下面的max-height数值就可以看到效果了-->
<!-- 技术来源于EricShulman，我是在论坛上看到他的回答保存下来的。-->
.colortext
   { font-variant:small-caps; color: red; }
.myTOC .tc-table-of-contents, .myTOC .tc-tabbed-table-of-contents-content
   { max-height:400px; overflow: hidden auto; }
</style>
<span class="myTOC">
<$macrocall
	$name="navx"
	tag="使太微更易用"
  selectedTiddler="$:/temp/toc/selectedTiddler"
	unselectedText="<p>选择目录中的一个主题，点击箭头可展开主题。</p>"
	missingText="<p>佚失条目。</p>"/>
</span>