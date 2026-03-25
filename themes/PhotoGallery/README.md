# PhotoGallery - Hugo Photo Gallery Theme

[中文](README.zh.md) | English

A clean, modern Hugo photo gallery theme inspired by Instagram. Perfect for photographers and visual artists who want to showcase their work in a beautiful, responsive gallery format.

## ✨ Features

- 🎨 **Instagram-style Design** - Clean, modern grid layout similar to Instagram
- 🌓 **Light/Dark Mode** - Automatic switching based on system preference, with manual toggle
- 📱 **Fully Responsive** - Optimized for mobile, tablet, and desktop
- 🖼️ **Multi-image Posts** - Display single or multiple photos in grid layouts
- 🏷️ **Tags & Categories** - Organize photos with tags
- 📷 **EXIF Information** - Display camera settings (model, lens, aperture, shutter, ISO, focal length)
- 🗺️ **Location Display** - Show where photos were taken
- 🚀 **Lazy Loading** - Performance-optimized image loading
- 🌍 **Multilingual** - Built-in support for English and Chinese
- 🔍 **SEO Friendly** - Semantic HTML and meta tags
- 📱 **PWA Ready** - Progressive Web App support

## 📸 Screenshots

| Light Mode | Dark Mode |
|------------|-----------|
| ![Light Mode](images/screenshot-light.png) | ![Dark Mode](images/screenshot-dark.png) |

## 🚀 Quick Start

### 1. Install Hugo

Make sure you have Hugo installed (version 0.112.0 or later):

```bash
hugo version
```

### 2. Create New Site

```bash
hugo new site my-gallery
cd my-gallery
```

### 3. Install Theme

Copy the `PhotoGallery` theme folder to your site's `themes/` directory:

```
my-gallery/
├── themes/
│   └── PhotoGallery/
├── content/
├── static/
└── hugo.toml
```

### 4. Configure

Create or edit `hugo.toml`:

```toml
baseURL = 'https://yourdomain.com'
languageCode = 'en'
title = 'My Photo Gallery'
theme = 'PhotoGallery'

[params]
    author = 'Your Name'
    description = 'A collection of my photography'
    defaultTheme = 'auto'  # Options: 'auto', 'light', 'dark'
    disableThemeToggle = false
    
    [params.footer]
        hideCopyright = false
        customText = ''

[menu]
    [[menu.main]]
        identifier = 'home'
        name = 'Home'
        url = '/'
        weight = 10
    [[menu.main]]
        identifier = 'about'
        name = 'About'
        url = '/about/'
        weight = 20

[pagination]
    pagerSize = 12

[markup]
    [markup.goldmark]
        [markup.goldmark.renderer]
            unsafe = true
```

### 5. Create Content

Create a new post:

```bash
hugo new content posts/my-photo-trip.md
```

### 6. Run Development Server

```bash
hugo server -D
```

Visit `http://localhost:1313` to see your site.

## 📝 Content Format

### Front Matter Example

```yaml
---
title: "Sunset at Santorini"
date: 2024-01-15T18:30:00+08:00
draft: false
summary: "A beautiful sunset captured in Oia, Santorini"
description: "The iconic blue-domed churches and white buildings of Santorini against a stunning sunset backdrop. Shot during golden hour from the famous Oia castle viewpoint."
location: "Oia, Santorini, Greece"
images:
  - url: "/images/santorini-1.jpg"
    caption: "Blue domes at sunset"
  - url: "/images/santorini-2.jpg"
    caption: "View from Oia castle"
  - url: "/images/santorini-3.jpg"
    caption: "Traditional architecture"
tags:
  - santorini
  - greece
  - sunset
  - travel
camera:
  model: "Sony A7IV"
  lens: "24-70mm GM II"
  aperture: "f/8"
  shutter: "1/125s"
  iso: "100"
  focal_length: "35mm"
---

Write your story here using **Markdown** formatting.
```

### Field Reference

| Field | Description | Required |
|-------|-------------|----------|
| `title` | Post title | ✅ Yes |
| `date` | Publication date | ✅ Yes |
| `draft` | Draft status | No (default: false) |
| `summary` | Short description for list view | No |
| `description` | Full description for detail page | No |
| `location` | Where the photo was taken | No |
| `images` | Array of image objects | No |
| `images[].url` | Image URL or path | No |
| `images[].caption` | Image caption | No |
| `tags` | List of tags | No |
| `camera` | Camera and settings info | No |

### Image Display Patterns

The theme automatically creates beautiful layouts based on image count:

| Image Count | Layout |
|-------------|--------|
| 1 | Single large image |
| 2 | Side-by-side (1:1 ratio) |
| 3 | First image spans 2 columns, 2 images below |
| 4+ | 2×2 grid (first 4 images, with counter badge) |

## 🎨 Customization

### Theme Colors

The theme uses CSS variables for easy customization. Override in your custom CSS:

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

### Custom CSS

Create custom CSS files in your site's `assets/css/` directory.

### Custom Fonts

Add custom fonts by placing font files in `static/fonts/` and referencing them in custom CSS.

## 🌍 Multilingual Setup

Add languages in `hugo.toml`:

```toml
[languages]
  [languages.en]
    languageName = "English"
    weight = 1
  [languages.zh]
    languageName = "中文"
    weight = 2
```

Create content for each language:
- `content/posts/hello.en.md`
- `content/posts/hello.zh.md`

## 📦 Production Build

Build your site for production:

```bash
hugo --minify
```

The generated site will be in the `public/` directory.

## 📋 Requirements

- Hugo 0.112.0 or later
- Modern web browser with CSS Grid support

## 🔧 Troubleshooting

### Images not loading
- Ensure images are in `static/images/` or use full URLs
- Check image file extensions match exactly (case-sensitive)

### Theme toggle not working
- Make sure `disableThemeToggle = false` in params
- Check browser console for JavaScript errors

### Layout issues
- Clear browser cache
- Verify Hugo version is 0.112.0+

## 📝 License

MIT License - see [LICENSE](LICENSE) file

## 🙏 Credits

- Inspired by Instagram's clean design
- Built with Hugo static site generator

---

Made with ❤️ for photographers everywhere
