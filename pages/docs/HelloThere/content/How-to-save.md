---
title: 如何保存
---

直接在网页上保存你的改动通常是无效的，[你的改动不会被保存下来](如何保存内容到社区仓库里)，有几个常用应用或内置功能可以用于真正地保存和备份你的笔记：

## 常用应用

### 桌面端

[TidGi太记](#TidGi%E5%A4%AA%E8%AE%B0)：跨平台桌面版应用，可以同时启动多个Wiki，每个Wiki保存为一个文件夹，文件夹里每条笔记都保存为单独的文件，并通过Git在节约空间的情况下保存多个历史版本备份。推荐使用此应用，可以减少很多折腾和配置的时间，直接用起来。

[TiddlyDesktop](#TiddlyDesktop)：跨平台桌面版应用，也可以同时启动多个Wiki，每个Wiki保存为一整个HTML文件，可以手动备份HTML文件，通过网盘可以让HTML文件在移动端打开。

### 移动端/跨平台

推荐 Android 手机用户使用开源免费的[Tiddloid](#Tiddloid)。

i0S 则使用 Quine2 等 AppStore 里的付费应用 。

不论使用 Android 还是 i0S 手机 ， 都可以使用[TW-MobiLe-Sync手机移动端同步桌面端插件](#TW-MobiLe-Sync%E6%89%8B%E6%9C%BA%E7%A7%BB%E5%8A%A8%E7%AB%AF%E5%90%8C%E6%AD%A5%E6%A1%8C%E9%9D%A2%E7%AB%AF%E6%8F%92%E4%BB%B6)和[TidGi太记](#TidGi%E5%A4%AA%E8%AE%B0)同步数据。

## 常用插件

### 手机和电脑同步数据

## 内置功能

以下是其它高级功能，新手建议只使用太记，在真正上手后再折腾这些高级内容，以免浪费时间和丢失数据。

### 保存到 GitHub 

使用 GitHub 在线保存、访问、修改和备份 TiddlyWiki。ps: 可能需科学上网

#在 TiddlyWiki 里填入以下信息 <br><img src="https://pic1.zhimg.com/v2-5a078b8340f46fc38edadba7fc7147c4_r.jpg">
#在 GitHub 上创建一个名为 wiki 的仓库，所有步骤都默认（可参考：<https://docs.github.com/cn/repositories/creating-and-managing-repositories/creating-a-new-repository> ）。再创建一个令牌并复制保存在本地（参照 <https://docs.github.com/cn/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token>）
#回到步骤一的 TiddlyWiki ，将令牌填入，点侧边栏的红色按钮保存成功，按钮变灰。
#回到第二步的GitHub ，可见 index.html 已存入 wiki 库，但无法在线访问。需再创建一个 wiki 库的 GitHub 网站（参照 <https://docs.github.com/cn/pages/getting-started-with-github-pages/creating-a-github-pages-site#creating-your-site>），实现在线访问。
#打开刚刚创建的网站网址，可在修改在线 TiddlyWiki后，按步骤三将令牌填入，实现在线修改并保存。