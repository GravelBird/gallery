# PhotoGallery - Hugo 相册主题

中文 | [English](README.md)

一个类似 Instagram 风格的 Hugo 相册主题，专为摄影师和视觉艺术家设计，以美观的响应式画廊格式展示作品。

## ✨ 特性

- 🎨 **Instagram 风格设计** - 简洁现代的网格布局，类似 Instagram 的照片展示
- 🌓 **浅色/深色模式** - 支持浅色和深色模式切换，可跟随系统主题
- 📱 **响应式设计** - 完美支持移动端、平板和桌面端
- 🖼️ **多图展示** - 支持单张照片和多张照片的网格展示
- 🏷️ **标签分类** - 支持为照片添加标签和分类
- 📷 **EXIF 信息** - 支持显示相机参数（相机型号、镜头、光圈、快门、ISO、焦距）
- 🗺️ **位置信息** - 支持显示拍摄地点
- 🚀 **图片懒加载** - 自动图片懒加载优化性能
- 🌍 **国际化支持** - 支持多语言（中文、英文）
- 🔍 **SEO 友好** - 语义化 HTML 和元标签
- 📱 **PWA 支持** - 渐进式 Web 应用支持

## 📸 截图

| 浅色模式 | 深色模式 |
|----------|----------|
| ![浅色模式](images/screenshot-light.png) | ![深色模式](images/screenshot-dark.png) |

## 🚀 快速开始

### 1. 安装 Hugo

确保已安装 Hugo（版本 0.112.0 或更高）：

```bash
hugo version
```

### 2. 创建新站点

```bash
hugo new site my-gallery
cd my-gallery
```

### 3. 安装主题

将 `PhotoGallery` 主题文件夹复制到你站点的 `themes/` 目录：

```
my-gallery/
├── themes/
│   └── PhotoGallery/
├── content/
├── static/
└── hugo.toml
```

### 4. 配置站点

创建或编辑 `hugo.toml`：

```toml
baseURL = 'https://yourdomain.com'
languageCode = 'zh-CN'
title = '我的相册'
theme = 'PhotoGallery'

[params]
    author = '你的名字'
    description = '我的摄影作品展示'
    defaultTheme = 'auto'  # 选项: 'auto', 'light', 'dark'
    disableThemeToggle = false
    
    [params.footer]
        hideCopyright = false
        customText = ''

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

[markup]
    [markup.goldmark]
        [markup.goldmark.renderer]
            unsafe = true
```

### 5. 创建内容

创建新文章：

```bash
hugo new content posts/my-photo-trip.md
```

### 6. 运行开发服务器

```bash
hugo server -D
```

访问 `http://localhost:1313` 查看站点。

## 📝 内容格式

### Front Matter 示例

```yaml
---
title: "圣托里尼日落"
date: 2024-01-15T18:30:00+08:00
draft: false
summary: "在圣托里尼伊亚小镇拍摄的绝美日落"
description: "圣托里尼标志性的蓝色圆顶教堂和白色建筑，在日落时分的金色光线中显得格外美丽。这张照片拍摄于著名的伊亚城堡观景台。"
location: "希腊 圣托里尼 伊亚小镇"
images:
  - url: "/images/santorini-1.jpg"
    caption: "日落时分的蓝色圆顶"
  - url: "/images/santorini-2.jpg"
    caption: "从伊亚城堡俯瞰"
  - url: "/images/santorini-3.jpg"
    caption: "传统建筑"
tags:
  - 圣托里尼
  - 希腊
  - 日落
  - 旅行
camera:
  model: "Sony A7IV"
  lens: "24-70mm GM II"
  aperture: "f/8"
  shutter: "1/125s"
  iso: "100"
  focal_length: "35mm"
---

在这里使用 **Markdown** 格式编写文章内容。
```

### 字段说明

| 字段 | 说明 | 必填 |
|------|------|------|
| `title` | 文章标题 | ✅ 是 |
| `date` | 发布日期 | ✅ 是 |
| `draft` | 草稿状态 | 否（默认：false） |
| `summary` | 列表页显示的简短描述 | 否 |
| `description` | 详情页显示的完整描述 | 否 |
| `location` | 拍摄地点 | 否 |
| `images` | 图片对象数组 | 否 |
| `images[].url` | 图片 URL 或路径 | 否 |
| `images[].caption` | 图片说明 | 否 |
| `tags` | 标签列表 | 否 |
| `camera` | 相机和拍摄参数信息 | 否 |

### 图片展示布局

主题会根据图片数量自动创建美观的布局：

| 图片数量 | 布局 |
|----------|------|
| 1 | 单张大图 |
| 2 | 并排显示（1:1 比例） |
| 3 | 第一张占 2 列，下面两张各占 1 列 |
| 4+ | 2×2 网格（显示前 4 张，带计数徽章） |

## 🎨 自定义样式

### 主题颜色

主题使用 CSS 变量，便于自定义。在你的自定义 CSS 中覆盖：

```css
:root {
    --primary: #ff6b6b;
    --bg-color: #ffffff;
    --text-color: #333333;
    --border-color: #e0e0e0;
}

[data-theme="dark"] {
    --bg-color: #1a1a1a;
    --text-color: #e0e0e0;
    --border-color: #333333;
}
```

### 自定义 CSS

在站点 `assets/css/` 目录创建自定义 CSS 文件。

### 自定义字体

将字体文件放入 `static/fonts/` 目录，并在自定义 CSS 中引用。

## 🌍 多语言设置

在 `hugo.toml` 中添加语言配置：

```toml
[languages]
  [languages.zh]
    languageName = "中文"
    weight = 1
  [languages.en]
    languageName = "English"
    weight = 2
```

为每种语言创建内容：
- `content/posts/hello.zh.md`
- `content/posts/hello.en.md`

## 📦 生产构建

构建生产版本：

```bash
hugo --minify
```

生成的站点将在 `public/` 目录中。

## 📋 系统要求

- Hugo 0.112.0 或更高版本
- 支持 CSS Grid 的现代浏览器

## 🔧 常见问题

### 图片无法加载
- 确保图片放在 `static/images/` 目录或使用完整 URL
- 检查图片文件扩展名是否完全匹配（区分大小写）

### 主题切换不工作
- 确保参数中 `disableThemeToggle = false`
- 检查浏览器控制台是否有 JavaScript 错误

### 布局显示异常
- 清除浏览器缓存
- 确认 Hugo 版本为 0.112.0+

## 📝 许可证

MIT License - 详见 [LICENSE](LICENSE) 文件

## 🙏 致谢

- 设计灵感来自 Instagram 的简洁风格
- 使用 Hugo 静态站点生成器构建

---

用 ❤️ 为摄影师打造
