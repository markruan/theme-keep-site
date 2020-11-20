---
title: Keep 主题配置指南
date: 2020-11-18 10:00:00
tags: [Keep]
categories: [Keep教程]
sticky: 9999
---

本文详细讲解 Keep 主题配置文件 `_config.yml` 如何使用，附带图文教程，目录对应着 `_config.yml` 的配置项，方便查阅。

<!-- more -->

在使用过程中有任何疑问，请在评论区留言。

## base_info

```yml
base_info:
  title: Keep
  author: Keep team
  url: https://keep.xpoet.cn/
```

请在此处正确填写你的博客网站基本信息：

- `title` 你的网站名称（将显示在网站头部，如下图）
  ![image](https://cdn.jsdelivr.net/gh/XPoet/image-hosting@master/Keep-主题配置指南/image.1isn675kdk68.png)
- `author` 你的昵称（将显示在网站底部和文章内容页，如下图）
  ![image](https://cdn.jsdelivr.net/gh/XPoet/image-hosting@master/Keep-主题配置指南/image.wrm4hxtmatc.png)
  ![image](https://cdn.jsdelivr.net/gh/XPoet/image-hosting@master/Keep-主题配置指南/image.4keak1scok60.png)

- `url` 你的博客网站域名

## style

```yml
style:
  # Theme primary color
  primary_color: "#0066CC"

  # Image align position, value: left | center
  img_position: left

  # Left side width
  left_side_width: 260px

  # Mouse hover
  hover:
    shadow: true # shadow effect when the mouse hover
    scale: false # scale effect when the mouse hover

  # First screen
  first_screen:
    enable: true
    description: Welcome to use Hexo theme Keep
```

此处设置博客网站基本样式：

### `primary_color`

设置网站主题色，支持 rgb、rgba、十六进制格式，例如：`rgb(0, 102, 204)`、`rgba(0, 102, 204,0.8)`、`#0066cc`。建议使用 [Web 安全色](https://www.bootcss.com/p/websafecolors/)。

### `img_position`

设置文章内容页的图片排列位置，默认 `left`（靠左），可选：`left`、`center`（居中）。

### `left_side_width`

- 设置左侧 TOC 目录结构模块的宽度，一般情况下，你无需更改。如需设置，请保持单位为 `px`。
- 示例：
  ![image](https://cdn.jsdelivr.net/gh/XPoet/image-hosting@master/Keep-主题配置指南/image.37aynu43rzk0.png)

### `hover`

设置鼠标悬浮时的样式，可开启 `shadow` 和 `scale` 效果。

- `shadow` 阴影效果
- `scale` 缩放效果

### `first_screen`

Keep v3.0.0 新增的网站首屏模块，开启后将显示在网站首页。

- `enable` 是否开启首屏
- `description` 首屏描述
- 首屏开启状态示例：
  ![image](https://cdn.jsdelivr.net/gh/XPoet/image-hosting@master/Keep-主题配置指南/image.1a6hcqxfelkw.png)

## social_contact

```yml
social_contact:
  enable: false
  links:
    github: # your GitHub URL
    wechat: # your WeChat QR-Code URL
    weibo: # your WeiBo URL
    twitter: # your twitter URL
    facebook: # your facebook URL
    email: # your email
```

配置社交网络链接。**注意：仅在首屏开启状态下才生效！**
![image](https://cdn.jsdelivr.net/gh/XPoet/image-hosting@master/Keep-主题配置指南/image.697xorgcmog0.png)

## menu

```yml
menu:
  Home: /
  Archives: /archives
  # Categories: /categories
  # Tags: /tags
  # Links: /links
  # About: /about
  # ...
```

网站头部导航菜单，如需新增导航菜单，按上面格式填写，同时需要创建相对应的 Hexo 页面。

![image](https://cdn.jsdelivr.net/gh/XPoet/image-hosting@master/Keep-主题配置指南/image.1pnsdnyz5v1c.png)

新创建的 Hexo 项目并没有 categories（分类）、tags（标签）、about（关于）、links（友链）等页面，需要自己手动创建。

以创建「 about（关于）」页面为例：

1. 在 Hexo 博客目录下执行命令 `hexo new page about` ，即可在 `source` 目录下生成 about 文件夹。
2. 在 Keep 主题配置文件的 `menu` 下添加 `about`。
   ```yml
   menu:
     Home: /
     Archives: /archives
     # Categories: /categories
     # Tags: /tags
     # Links: /links
     About: /about
   ```
3. 打开博客目录下 `/source/about/index.md` 文件填写内容，即可显示在页面上。
   支持 Markdown 和 HTML 格式；`comment: true` 表示该页面开启评论功能。
   参考如下：

   ```markdown
   ---
   title: about
   date: 2020-03-19 14:59:53
   comment: true
   ---

   ## About me

   - XPoet「 Keep core developer 」...
     ...
     ...
     ...
   ```

   **注意自动生成的 `title` 属性不要修改！例如：`title: about` 无需修改！**

## rss

```yml
rss:
  enable: false
```

1. 启用 RSS 订阅功能，需先在 Hexo 博客根目录下安装插件 **`hexo-generator-feed`** 。

   ```bash
   npm install hexo-generator-feed
   ```

2. 在 Hexo 配置文件 `_config.yml` 增加如下配置项。

   ```yml
   # Feed Atom
   # npm install hexo-generator-feed
   feed:
     type: atom
     path: atom.xml
     limit: 20
   ```

3. RSS 订阅功能开启后，将会在**右下角**工具按钮组里面显示**RSS 按钮**。
   ![image](https://cdn.jsdelivr.net/gh/XPoet/image-hosting@master/Keep-主题配置指南/image.53felwifzyc0.png)

## comment

Keep 主题目前内置两款评论插件：Valine 和 Gitalk，你只能使用其中一款，如果两款评论插件的 enable 都设为了 true，将使用 Valine。

### Valine

Valine 诞生于 2017 年 8 月 7 日，是一款基于 LeanCloud 的快速、简洁且高效的无后端评论系统。

详情查看：

- https://github.com/xCss/Valine/
- https://valine.js.org/

在 Keep 中如何使用：

1. 请先 [登录](https://leancloud.cn/dashboard/login.html#/signin) 或 [注册](https://leancloud.cn/dashboard/login.html#/signup) LeanCloud，进入控制台后点击左下角创建应用。

   ![image](https://cdn.jsdelivr.net/gh/XPoet/image-hosting@master/Keep-主题配置指南/image.1wxzxd3182v4.png)

2. 应用创建好以后，进入刚刚创建的应用，选择左下角的`设置` > `应用Key`，然后就能看到你的 `APP ID` 和 `APP Key` 了。

   ![image](https://cdn.jsdelivr.net/gh/XPoet/image-hosting@master/Keep-主题配置指南/image.33nt46l951k0.png)

3. 在 Keep 主题配置文件填写必要参数信息（APP ID、APP Key 等），示例如下。

   ```yml
   valine:
     enable: true
     appid: ih2nzxxxxxxxxxxxxxxxxxxxxxx
     appkey: gdf6666666666666666666666666
     meta: ["nick", "mail", "link"]
     placeholder: 😜 尽情吐槽吧~
   ```

   - `appid` 必填。
   - `appkey` 必填。
   - `meta` 可填，表示评论框的要填写的信息（昵称、邮箱、链接）。
   - `placeholder` 可填，表示评论框的在还没输入内容时的显示的信息。

4. Valine 评论插件效果图。
   ![image](https://cdn.jsdelivr.net/gh/XPoet/image-hosting@master/Keep-主题配置指南/image.5kmcm9ur27c0.png)

### Gitalk

Gitalk，一个基于 Github Issue 和 Preact 开发的评论插件。

详情查看：

- https://github.com/gitalk/gitalk

在 Keep 中如何使用：

1. 新建 GitHub OAuth App
   注册或登录 GitHub，创建新的 OAuth App，链接：https://github.com/settings/applications/new ，其中 `Homepage URL` 和 `Authorization callback URL` 均填写自己的域名即可。

   把 `Client ID` 和 `Client Secret` 保存起来。

   ![image](https://cdn.jsdelivr.net/gh/XPoet/image-hosting@master/Keep-主题配置指南/image.63klvgf0bz80.png)

2. 新建 GitHub 仓库
   注册或登录 GitHub，创建一个[新的仓库（repository）](https://github.com/new)，并打开 Issues（自己手动增加一个 Issue），用于存储评论内容。

3. 把自己的 `GitHub 用户名称`、`仓库名称` 、OAuth App 的 `Client ID` 、`Client Secret` 分别填写在主题配置文件里，如下示例。

   ```yml
   gitalk:
     enable: true
     github_id: XPoet
     repository: ils-site-comments
     client_id: cdfffffffffffffffffffff
     client_secret: f4b55555555555555555555555555555
   ```

4. Gitalk 评论插件效果图。
   ![image](https://cdn.jsdelivr.net/gh/XPoet/image-hosting@master/Keep-主题配置指南/image.62gtta1e2lo0.png)

## website_count

Keep 主题内置“不蒜子”计数，无需额外配置，选择你要开启的计数项即可。

```yml
busuanzi_count:
  enable: true
  site_uv: true
  site_pv: true
  page_pv: true
```

- `site_uv` 网站访问人数
- `site_pv` 网站总访问量
- `page_pv` 文章阅读次数

计数效果图如下：
![image](https://cdn.jsdelivr.net/gh/XPoet/image-hosting@master/Keep-主题配置指南/image.7upexmtx174.png)
![image](https://cdn.jsdelivr.net/gh/XPoet/image-hosting@master/Keep-主题配置指南/image.4c2gxkwikjy0.png)

## local_search

博客网站文章的搜索功能，非常实用，强烈建议开启。开启后，右上角将出现**搜索按钮**。

![image](https://cdn.jsdelivr.net/gh/XPoet/image-hosting@master/Keep-主题配置指南/image.2bwatod85l3w.png)

在 Keep 主题中如何使用：

1. 启用本地搜索功能，需在 Hexo 博客根目录下安装插件 `hexo-generator-searchdb` 。

   ```bash
   npm install hexo-generator-searchdb
   ```

2. 修改主题配置文件 `_config.yml` 的 local_search 配置项。

   ```yml
   local_search:
     enable: true
     trigger: auto
     unescape: false
     preload: true
   ```

   - `trigger` 搜索触发方式，输入关键字后会触发搜索，可选 auto（自动）或 manual（手动）。

     - auto 每输入或删除一个字符后，自动触发搜索。
     - manual 每输入或删除一个字符后，需要按回车键触发搜索。

   - `unescape` 转义 HTML 字符串为可读字符串。
   - `preload` 在页面加载时预加载搜索数据。

3. 搜索功能效果图。

   ![image](https://cdn.jsdelivr.net/gh/XPoet/image-hosting@master/Keep-主题配置指南/image.5ncps0hxep80.png)

## post_wordcount

文章字数统计和阅读时长统计功能。

如何使用：

1. 如需启用，请先安装 Hexo 插件：hexo-wordcount。
   在博客根目录下使用 npm 命令安装: `npm i hexo-wordcount --save`

2. 在主题配置文件中开启。

   ```yml
   post_wordcount:
     enable: true
     wordcount: true
     min2read: true
   ```

   - `wordcount` 文章字数统计。
   - `min2read` 阅读时长统计。

3. 效果图。
   ![image](https://cdn.jsdelivr.net/gh/XPoet/image-hosting@master/Keep-主题配置指南/image.5kbf5mw7s1c0.png)

## home_article

首页文章块底部的显示设置。

```yml
home_article:
  category:
    enable: true
    limit: 3
  tag:
    enable: true
    limit: 5
```

- `enable` 表示是否开启显示。
- `limit` 表示显示的最大个数。
- 效果图。
  ![image](https://cdn.jsdelivr.net/gh/XPoet/image-hosting@master/Keep-主题配置指南/image.2607j4z3haio.png)

## code_copy

代码复制功能。

```yml
code_copy:
  enable: true
  style: default # values: default | mac
```

- `enable` 是否开启。

- `style` 代码复制的样式，可选 `default` 和 `mac`。

  - `default` 效果图
    ![image](https://cdn.jsdelivr.net/gh/XPoet/image-hosting@master/Keep-主题配置指南/image.5pl9cgmd2es0.png)

  - `mac` 效果图
    ![image](https://cdn.jsdelivr.net/gh/XPoet/image-hosting@master/Keep-主题配置指南/image.34hxsn6nw260.png)

## side_tools

是否开启右下角的工具按钮。

```yml
side_tools:
  enable: true
```

- 未展开状态
  ![image](https://cdn.jsdelivr.net/gh/XPoet/image-hosting@master/Keep-主题配置指南/image.7cp2ei44ih80.png)

- 展开状态
  ![image](https://cdn.jsdelivr.net/gh/XPoet/image-hosting@master/Keep-主题配置指南/image.6m5di5o3h2c0.png)

## back2top

一键快速 `回到顶部` 和 `到达底部` 功能。

```yml
back2top:
  enable: true
```

- 点击 `↑ 上箭头` 即可快速回到网站`顶部`。
- 点击 `↓ 下箭头` 即可快速到达网站`底部`。

![image](https://cdn.jsdelivr.net/gh/XPoet/image-hosting@master/Keep-主题配置指南/image.6lh91v7gmwo0.png)

## toc

文章目录结构，非常实用的功能，方便查看文章结构和跳转，强烈建议开启。

```yml
toc:
  enable: true

  # Automatically add list number to toc.
  number: true

  # If true, all level of TOC in a post will be displayed, rather than the activated part of it.
  expand_all: true
```

- `number` 目录结构是否显示数字序号。

- `expand_all` 是否展开所有目录结构。
  - `expand_all: true` 初始已展开所有的目录结构。
  - `expand_all: false` 边滚动页面边展开对应的位置的目录。

## copyright_info

```yml
copyright_info:
  enable: true
```

文章内容页的版权信息模块。

![image](https://cdn.jsdelivr.net/gh/XPoet/image-hosting@master/Keep-主题配置指南/image.4muim0yrzbe0.png)

## footer

```yml
footer:
  since: 2020
```

网站最底部的信息展示设置。

- `since` 设置网站起始年份
- 示例
  ![image](https://cdn.jsdelivr.net/gh/XPoet/image-hosting@master/Keep-主题配置指南/image.2v9fbvcrt720.png)
