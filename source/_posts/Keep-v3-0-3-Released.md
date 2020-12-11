---
title: Keep v3.0.3 Released
date: 2020-12-01 12:00:00
tags:
  - Keep
  - 更新日志
categories:
  - 更新日志
---

1. 修复用户无法使用自己图片作为 **头像(avatar)** 和 **网站图标(favicon)** 的 Bug。

1. 主题配置文件增加 `favicon` 和 `avatar` 配置选项，可使用**本地图片**或**图片外链**。

   ```yml
   style:
     # Theme primary color
     primary_color: "#CC3333"

     # Avatar (You can use local image or image external link)
     avatar: https://cdn.jsdelivr.net/gh/XPoet/image-hosting@master/common-use/avatar.jpg

     # Favicon (You can use local image or image external link)
     favicon: images/logo.svg
   ```

1. 重构 CSS 字体单位，`em` -> `rem`，更合理，更协调，更优雅。
