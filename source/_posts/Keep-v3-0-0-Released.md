---
title: Keep v3.0.0 Released
date: 2020-11-26 12:00:00
tags:
  - Keep
  - 更新日志
categories:
  - 更新日志
---

1. 增加首屏展示功能。

   ```yml
   style:
   # First screen
   first_screen:
     enable: true
     description: Keep writing and Keep loving.
   ```

1. 增加第三方社交链接功能。

   ```yml
   social_contact:
   enable: false
   links:
       github: https://github.com/XPoet
       weixin: https://xxx.com
       ......
   ```

1. 增加在线字号调整功能。

1. 重构右下角侧边工具栏。

1. 增加自由切换内容区域宽度功能。

1. 升级 fontawesome 图标库。

1. 增加设置 CDN 加速功能。

  ```yml
  cdn:
    enable: true
  ```

1. 增加底部起始年份设置功能。

   ```yml
   footer:
     since: 2020
   ```

1. 优化 Markdown 样式。

1. 移除原 ILS 的 magic 配置项 和 normal 风格。

1. 美化友链页面样式并采用 `_data` 来存储。

  links.yml

   ```yml
   - name: XPoet
     link: https://xpoet.cn/
     description: 懒惰是程序员第一生产力
     avatar: https://cdn.jsdelivr.net/gh/XPoet/image-hosting@master/common-use/avatar.jpg

   - name: 不知名艺术家
     link: https://jinzhanqi.com/
     description: love artist, love code.
     avatar: https://s3.ax1x.com/2020/11/17/DVvkB4.jpg

   - name: xxx
     link: https://xxx.com/
     description: xxx
     avatar: xxx
   ```

1. 首页文章块显示该文章创建于多久之前。

1. 文章内容页增加版权信息模块。

1. 文章内容页增加大图查看器。

1. ......
