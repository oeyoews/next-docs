---
title: 使用插件源
---

### 从插件源安装插件

太记自带了几个插件源，点击右上角页面工具栏里的 {{$:/core/images/options-button}} 按钮，打开[控制面板]($:/ControlPanel)，然后打开控制面板条目里「插件」标签页。

这时你会看到一个「获取更多插件」按钮，点击它，就会加载当前安装了的插件源里的插件列表了。

### 安装官方插件源

如果你是用 NodeJS 版的，有可能无法安装官方插件，不过可以将[$:/config/OfficialPluginLibrary](#%24%3A/config/OfficialPluginLibrary)拖入你的 Wiki，就可以解锁安装官方插件了。

以[太微中文社区插件库]($:/config/ChinesePluginLibrary/Netlify)为例，只要用鼠标把左边这个插件库条目链接拖到你自己的 Wiki 里，并点击出现的确认导入按钮，就算装好了。

插件库不会自动更新，[杰里米](杰里米·拉斯顿)觉得这样对隐私不好。所以需要手动更新。手动更新就是去[官网](https://tiddlywiki.com/)把[$:/config/OfficialPluginLibrary](#%24%3A/config/OfficialPluginLibrary)再导入一遍。不会出现重复导入的问题。

关于条目拖动的原理和更多用法，详见[拖动资源](#%E6%8B%96%E5%8A%A8%E8%B5%84%E6%BA%90)。