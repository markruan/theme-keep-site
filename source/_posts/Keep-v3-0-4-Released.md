---
title: Keep v3.0.4 Released
date: 2020-12-7 12:00:00
tags:
  - Keep
  - 更新日志
categories:
  - 更新日志
---

1. 优化首屏描述的字体样式，调整行高和大小。

1. 主题配置文件增加首屏背景图片 `background_img` 配置选项，可使用**本地图片**或**图片外链**。

   ```yml
   first_screen:
     enable: true
     + background_img: /images/bg.svg
     description: Keep writing and Keep loving.
   ```
1. 修改 RSS 图标缺失的 Bug。

1. 优化友链页面在移动端的样式。
