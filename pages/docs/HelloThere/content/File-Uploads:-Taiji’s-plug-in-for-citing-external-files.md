---
title: File Uploads：太记的引用外部文件插件
---

(待补充)

如果在Webdav服务器的部署下我们可以使用FileUploads、File Uploads: PUT插件实现在本地保存图片的功能，如果要保存其它类型的文件，可以通过修改Filter实现。

需要在webdav服务器、github、nodejs环境下使用FileUploads及子插件并配置好相关的设置。

在使用图片的时候程序会判断大于100k时会自动保存到配置好的文件夹中。