---
title: 排查nodejs加载慢
---

首先进到一个 tw npm 包文件夹里，例如

```shell
cd /xxx/TiddlyGit-Desktop/node_modules/@tiddlygit/tiddlywiki
```

然后加载一个wiki文件夹，以 `/xxx/wiki/wiki` 为例就是

```shell
node -prof ./tiddlywiki.js +plugins/tiddlywiki/filesystem +plugins/tiddlywiki/tiddlyweb /xxx/wiki/wiki --listen root-tiddler=$:/core/save/lazy-images
```

注意是用 node 去执行 tiddlywiki 的入口 JS 文件，你也可以写成 `node --prof-process --preprocess ./node_modules/tiddlywiki/tiddlywiki/tiddlywiki.js` 之类的。

这会在之前 cd 进去的文件夹 `node_modules/@tiddlygit/tiddlywiki` 里生成一个名字如 `isolate-0x7faf7ea00000-58485-v8.log` 的文件，我们需要把它转换成火焰图文件：

```shell
node --prof-process --preprocess  /xxx/isolate-0x7faf7ea00000-58485-v8.log > ~/Desktop/out.json
```

然后把生成出来的文件拖到 <https://mapbox.github.io/flamebearer/> 里就可以查看啦！