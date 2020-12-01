---
title: changelog
date: 2020-10-29 21:44:16
comment: true
---

> 重要通知：
> 自 `v3.0.0` 起，原 Hexo 主题 ILS 改名为 **Keep**， `v3.0.0` 在原 ILS 基础上做了大量改进、优化和代码重构，同时也新增许多功能，强烈建议使用最新版本 Keep 主题及最新版本的主题配置文件 `_config.yml`。


# v3.0.3 [2020-12-01]

1. 修复用户无法使用自己图片作为 **头像(avatar)** 和 **网站图标(favicon)** 的 Bug。

1. 主题配置文件增加 `favicon` 和 `avatar` 配置选项，可使用本地图片或 CDN 外链。
   ```yml
   style:
     # Theme primary color
     primary_color: '#CC3333'
   
     # Avatar (You can use local image or image external link)
     avatar: images/avatar.png
   
     # Favicon (You can use local image or image external link)
     favicon: images/logo.svg
   ```

1. 重构 CSS 字体单位，`em` -> `rem`，更合理，更协调，更优雅。


# v3.0.0 [2020-11-26]

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
       weixin: xxx
       ......
   ```

1. 增加在线字号调整功能。

1. 重构右下角侧边工具栏。

1. 增加自由切换内容区域宽度功能。

1. 升级 fontawesome 图标库。

1. 增加设置 CDN 加速功能。

1. 增加底部起始年份设置功能。

1. 优化 Markdown 样式。

1. 移除原 ILS 的 magic 配置项 和 normal 风格。

1. 美化友链页面并采用 \_data 来存储。

1. 首页文章块显示该文章创建于多久之前。

1. 文章内容页增加版权信息模块。

1. ......


# v2.1.3 [2020-10-30]

1. **文章顶置的属性改为 `sticky`，无需安装第三方插件。**

   ```
   ---
   title: ILS 主题配置文件图文教程
   date: 2020-10-30 10:26:05
   sticky: 9999
   ---
   ```

2. **新创建的页面添加评论功能的属性改为 `comment`。**
   `_config.yml` 主题配置文件的评论属性也需要修改 `comments` -> `comment`，**强烈建议**使用最新版的 `_config.yml`。

   ```
   ---
   title: changelog
   date: 2020-10-29 21:44:16
   comment: true
   ---
   ```

3. 文章内容页增加博主头像图片和`Lv`标识，`Lv`等级根据文章数量判断。
4. 优化 Gitalk 评论插件，适配夜间模式。
