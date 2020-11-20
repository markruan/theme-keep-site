---
title: Keep 代码贡献指南
date: 2020-11-18 11:00:00
tags: [Keep]
categories: [Keep教程]
sticky: 9998
---

参与 Keep 主题开发非常简单，总体框架作者已经搭建好了，你只需在此基础上添砖加瓦，包括但不限于：美化样式、增加功能、改进代码、 修复 Bug 等。

期待你的贡献！

<!-- more -->

## Keep 目录结构

```
/keep
├── _config.yml
├── languages
├── layout
├── scripts
└── source
```

- `_config.yml`
  Keep 主题的配置文件，在此处添加新的配置项。

- `languages`
  Keep 主题的语言文件夹，在此处添加新的语言配置项，目前只有中文和英文，欢迎添加其他语言。

- `layout`
  Keep 主题的布局文件夹，用于存放主模板文件，决定网站内容的呈现方式。
  请在此处添加新的模板，参考 [模板](https://hexo.io/zh-cn/docs/templates) 以获得更多信息。

- `scripts`
  脚本文件夹。在启动时，Hexo 会载入此文件夹内的 JavaScript 文件，参考 [插件](https://hexo.io/zh-cn/docs/plugins) 以获得更多信息。

- `source`
  资源文件夹，除了模板以外的资源，例如 CSS、JavaScript、图片、字体文件等，都放在这个文件夹中。

## Keep 技术栈

- EJS
  Keep 使用 EJS 模板引擎，你只需掌握几个 EJS 简单的语法，便可上手参考开发。
  参考：https://ejs.bootcss.com/

- Stylus
  Keep 使用 Stylus CSS 预处理器，使得 CSS 写法更灵活，你只需掌握 Stylus 基本语法，便可上手参考开发。
  参考：https://stylus.bootcss.com/

## Keep Plan Todo

- [ ] 图片懒加载
- [ ] 文章点赞功能
- [ ] 文章打赏
- [ ] 在线更改字体
- ...

## 参与开发流程

假设你想为 Keep 主题增加 **“文章版本信息”** 模块，可参考下列流程：

### Fork Keep repository

请先 **Fork** Keep 代码仓库到你的 GitHub，然后通过 Git 克隆你自己的 GitHub 账号下的 Keep 仓库。

### Clone Keep

使用 git 克隆你 GitHub 账号下的 Keep 到 Hexo 项目中。

```
git clone --depth=1 git@github.com:你的GitHub用户名/hexo-theme-keep.git themes/keep
```

### 启动 Hexo 服务

启动 Hexo 服务，在开发过程中，实时查看 Keep 主题页面效果。

```
hexo s -o
```

### 创建 Keep 模板文件

- 请在 `layout` 文件夹里创建 Keep 模板文件，以 **“文章版本信息”** 模块为例，因为是一个比较小的模块，所以在 `layout/_partial` 文件夹中创建 `copyright-info.ejs` 这个新模板文件。

- 在 `copyright-info.ejs` 文件中编写你的 HTML 结构代码，边修改边在浏览器查看效果。

### 创建 Keep 样式文件

- 请在 `source/css/layout` 文件夹里创建 Keep 样式文件，同上，在 `source/css/layout/_partial` 文件夹中创建 `copyright-info.styl` 样式文件。

- 在 `copyright-info.styl` 文件中编写你的 CSS 样式代码，建议边修改边在浏览器查看效果。

### 编写业务逻辑代码

如果你想添加的功能业务逻辑比较复杂，请在 `source/js/utils.js` 这个 JS 文件里面编写，或新建一个单独 JS 文件。

注意，你新建的 JS 文件别忘了引入，可在 `layout/_partial/scripts.ejs` 文件中统一管理。

### 提交代码

当你想要添加的功能模块开发完毕之后，**请检查一下有无 Bug**，确认无误后，`commit` 并且 `push` 到你的 GitHub 仓库。

### 发起 Pull Request

当你 GitHub 上的 Keep 仓库有代码更新，便可向作者的 Keep 仓库发起一个 [Pull Request](https://juejin.im/post/6844903856971710477)，然后填写描述信息，等待作者合并代码。

## 参考链接

- Hexo 主题 https://hexo.io/zh-cn/docs/themes
- Hexo 模板 https://hexo.io/zh-cn/docs/templates
- Hexo 插件 https://hexo.io/zh-cn/docs/plugins
- Hexo 变量 https://hexo.io/zh-cn/docs/variables

