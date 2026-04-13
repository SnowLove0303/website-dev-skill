---
name: website-dev
description: "🎯 宣传网站完整开发技能包 - 从0到1交付高质量网站"
version: 2.0
date: 2026-04-13
整合: frontend-checklist, web-testing, web-accessibility, web-seo, web-performance, projects-reference, animation-library, tailwind-components
---

# 🎯 网站开发技能包 v2.0

> 织梦出品 | 宣传网站从规划到上线的完整解决方案

---

## 🚀 开发流程

```
需求确认 → 技术方案 → 编码实现 → 自检测试 → 交付上线
```

---

## 📋 Part 1: HTML/CSS/JS 编码规范

### 基础 HTML 模板
```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>页面标题 - 品牌名 | 50-60字符</title>
  <meta name="description" content="页面描述，150-160字符，包含核心关键词">
  <meta property="og:title" content="分享标题">
  <meta property="og:description" content="分享描述">
  <meta property="og:image" content="分享图片链接">
  <link rel="canonical" href="标准URL">
  <link rel="preconnect" href="https://fonts.googleapis.com">
</head>
<body>
  <header><nav></nav></header>
  <main><section></section></main>
  <footer></footer>
</body>
</html>
```

### 语义化标签
`<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, `<footer>`
⚠️ 按钮用 `<button>`，链接用 `<a>`，不要用 div 伪装

### 图片规范
```html
<img src="photo.jpg" alt="描述文字" loading="lazy" width="800" height="600">
<picture>
  <source srcset="image.webp" type="image/webp">
  <img src="image.jpg" alt="描述">
</picture>
```

### 链接规范
✅ `<a href="/about">关于我们</a>`
❌ `<a href="/about">点击这里</a>`

---

## 📋 Part 2: CSS 规范

### 响应式断点
```css
body { font-size: 14px; }  /* 移动优先 */
@media (min-width: 768px) { }  /* 平板 */
@media (min-width: 1024px) { } /* 桌面 */
```

### 点击区域 ≥44px
```css
button, a { min-height: 44px; min-width: 44px; padding: 12px 16px; }
```

### 焦点样式（必须！）
```css
:focus-visible { outline: 2px solid #0066cc; outline-offset: 2px; }
```

---

## 📋 Part 3: SEO 清单

### 必须有
- [ ] title（50-60字符）
- [ ] meta description（150-160字符）
- [ ] viewport
- [ ] og:title / og:description / og:image
- [ ] 图片 alt
- [ ] 一个 H1（包含关键词）
- [ ] canonical

---

## 📋 Part 4: 无障碍(A11y)

### WCAG 2.1 AA
- [ ] 颜色对比度 ≥ 4.5:1
- [ ] 所有图片有 alt
- [ ] 表单有 label
- [ ] Tab 键可导航
- [ ] focus 可见

### 常用 ARIA
```html
<button aria-label="关闭">X</button>
<div aria-hidden="true">装饰</div>
```

---

## 📋 Part 5: 性能优化

### Core Web Vitals
| 指标 | 达标 | 优秀 |
|------|------|------|
| LCP | ≤2.5s | ≤1.5s |
| CLS | ≤0.1 | ≤0.05 |
| INP | ≤200ms | ≤100ms |

### 字体优化
```css
@font-face { font-display: swap; }
```

---

## 📋 Part 6: 动画效果

### Animate.css
```html
<link href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css">
<h1 class="animate__animated animate__bounce">弹跳</h1>
```
常用：fadeIn, fadeInUp, slideInLeft, zoomIn, bounce

### AOS 滚动动画
```html
<link href="https://unpkg.com/aos@2.3.1/dist/aos.css">
<script src="https://unpkg.com/aos@2.3.1/dist/aos.js"></script>
<div data-aos="fade-up">淡上入场</div>
<script>AOS.init();</script>
```

### GSAP 复杂动画
```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js"></script>
<script>
gsap.from('.fade-in', { opacity: 0, y: 50, duration: 1 });
</script>
```

### 常用效果（50projects50days）
| 效果 | 场景 |
|------|------|
| Expanding Cards | 产品展示 |
| Scroll Animation | 视差滚动 |
| Progress Steps | 分步引导 |
| FAQ Collapse | 问答折叠 |
| Toast Notification | 反馈提示 |

---

## 📋 Part 7: Tailwind CSS + DaisyUI

### CDN 快速开始
```html
<script src="https://cdn.tailwindcss.com"></script>
<link href="https://cdn.jsdelivr.net/npm/daisyui@4.4.19/dist/full.min.css" rel="stylesheet">
```

### 常用组件
```html
<!-- 按钮 -->
<button class="btn">默认</button>
<button class="btn btn-primary">主要</button>
<button class="btn btn-ghost">幽灵</button>

<!-- 卡片 -->
<div class="card w-96 bg-base-100 shadow-xl">
  <figure><img src="photo.jpg" alt=""/></figure>
  <div class="card-body">
    <h2 class="card-title">标题</h2>
    <p>内容</p>
    <div class="card-actions justify-end">
      <button class="btn btn-primary">按钮</button>
    </div>
  </div>
</div>

<!-- 导航 -->
<div class="navbar bg-base-100 shadow">
  <a class="btn btn-ghost text-xl">Logo</a>
</div>

<!-- 徽章 -->
<span class="badge badge-primary">新</span>

<!-- 折叠 -->
<div class="collapse collapse-arrow">
  <input type="radio" name="my-accordion">
  <div class="collapse-title">点击展开</div>
  <div class="collapse-content"><p>内容</p></div>
</div>
```

---

## 📋 Part 8: 自动化测试

### 运行测试
```bash
cd skills/web-testing
python run_tests.py
```

### 修改地址
编辑 `run_tests.py` 第10行：
```python
SITE_URL = "http://localhost:5500"
```

### 测试项目
| 测试 | 内容 |
|------|------|
| 页面加载 | HTTP 状态码 |
| 标题 | title 存在 |
| 语义化 | header/main/footer/nav |
| 链接 | 检测外部死链 |
| 响应式 | 桌面/平板/手机 |
| SEO | meta 标签 |

---

## 📊 质量目标

### Lighthouse
| 指标 | 目标 |
|------|------|
| Performance | 90+ |
| Accessibility | 90+ |
| SEO | 90+ |

---

## 📁 项目结构

```
project/
├── index.html
├── about.html
├── css/
│   ├── reset.css
│   └── main.css
├── js/
│   └── main.js
├── images/
└── assets/
```

---

## ⚠️ 开发原则

### 必须先确认
- HTML 结构修改
- CSS 布局调整
- 功能逻辑改动

---

*整合了 8 个子模块 | 最后更新：2026-04-13*
