---
title: 基于 Hugo 和 Decap CMS 使用 Github 作为后端在 Cloudflare Pages 上免费搭建博客网站
slug: hugo-decap-cms-github-cloudflare-pages-blog
date: 2024-12-25T00:00:00.000Z
description: 本篇文章将详细介绍如何利用 Hugo、Decap CMS、GitHub 和 Cloudflare 免费搭建一个功能齐全的博客网站。
image: /img/hugo-decap-cms-github-cloudflare-pages-blog.webp
categories:
  - Jamstack
---
## 普通步骤

### 安装 hugo（需 go 语言环境）

```shell
go install github.com/gohugoio/hugo@latest
```

### 使用 hugo 创建网站

```shell
hugo new site blog
cd blog
git init
# 这里我使用的是 stack 主题
git submodule add https://github.com/CaiJimmy/hugo-theme-stack.git themes/stack
# 设置主题为 stack
echo "theme = 'ananke'" >> hugo.toml
```

### 添加 Decap CMS

为刚才创建的 hugo 网站添加 Decap CMS 管理后台文章

### 配置 Cloudflare Pages

## 快捷步骤

```shell
git clone https://github.com/Danielxxf/my-blog.git
```
