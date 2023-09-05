---
title: 太微的数据如何存储
---

太微最初是一个单HTML文件形式的知识库程序，所以太微的数据一开始是保存在用户本地的浏览器内的。

<div id="tiddlywiki-save-graph">
<$mermaid text='
  graph TD;
    浏览器内存 --> 本地硬盘
		浏览器内存 --内置Git保存器--> Git服务器
    本地硬盘 --太记桌面版--> Git服务器
    浏览器内存 --相关插件--> WebDav/自建云服务器
    浏览器内存 --SoLiD或IPFS插件--> Web3
'></$mermaid>
</div>

<style>
.tamasha-slide-content #tiddlywiki-save-graph {
	line-height: 1.2rem !important;
}
</style>