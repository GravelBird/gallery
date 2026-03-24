# PhotoGallery - Hugo 相册主题

一个类似 Instagram 风格的 Hugo 相册主题，用于展示照片作品。

## 特性

- 🎨 **Instagram 风格设计** - 简洁现代的网格布局，类似Instagram的照片展示
- 🌓 **浅色/深色模式** - 支持浅色和深色模式切换，可跟随系统主题
- 📱 **响应式设计** - 完美支持移动端和桌面端
- 🖼️ **多图展示** - 支持单张照片和多张照片的网格展示
- 🏷️ **标签分类** - 支持为照片添加标签和分类
- 📷 **EXIF 信息** - 支持显示相机参数（相机型号、镜头、光圈、快门等）
- 🗺️ **位置信息** - 支持显示拍摄地点
- 🚀 **图片懒加载** - 自动图片懒加载优化性能
- 🌍 **国际化支持** - 支持多语言（中文、英文）

## 安装

1. 将主题复制到 `themes/PhotoGallery` 目录
2. 在 `hugo.toml` 中设置 `theme = 'PhotoGallery'`

## 配置

### hugo.toml 示例

```toml
baseURL = 'https://example.com'
languageCode = 'zh-CN'
title = '我的相册'
theme = 'PhotoGallery'

[params]
    author = '摄影师'
    description = '我的个人相册'
    defaultTheme = 'auto'  # auto, light, dark
    disableThemeToggle = false
    
    [params.footer]
        hideCopyright = false

[menu]
    [[menu.main]]
        identifier = 'home'
        name = '首页'
        url = '/'
        weight = 10
    [[menu.main]]
        identifier = 'about'
        name = '关于'
        url = '/about/'
        weight = 20

[pagination]
    pagerSize = 12
```

## 文章格式

创建相册文章时，使用以下Front Matter格式：

```yaml
---
title: "文章标题"
date: 2024-01-15T10:00:00+08:00
draft: false
summary: "文章摘要"
description: "详细描述"
location: "拍摄地点"
images:
  - url: "图片URL"
    caption: "图片说明"
  - url: "图片URL2"
    caption: "图片说明2"
tags:
  - 标签1
  - 标签2
camera:
  model: "相机型号"
  lens: "镜头"
  aperture: "光圈"
  shutter: "快门"
  iso: "ISO"
  focal_length: "焦距"
---

文章内容（支持Markdown格式）
```

## 字段说明

- `title`: 文章标题
- `date`: 发布日期
- `summary`: 摘要，显示在首页
- `description`: 详细描述，显示在详情页
- `location`: 拍摄地点
- `images`: 图片列表
  - `url`: 图片URL
  - `caption`: 图片说明
- `tags`: 标签列表
- `camera`: 相机信息
  - `model`: 相机型号
  - `lens`: 镜头
  - `aperture`: 光圈
  - `shutter`: 快门速度
  - `iso`: ISO值
  - `focal_length`: 焦距

## 多图展示

当一篇文章包含多张图片时，首页会以网格形式展示：
- 2张图片：2x1 网格
- 3张图片：第一张占2列，下面两张各占1列
- 4张图片：2x2 网格

右上角会显示图片数量徽章。

## 截图

（待添加）

## 许可

MIT License
