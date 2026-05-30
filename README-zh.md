# RicoUI Astro Starter

一个以设计为驱动的 Astro starter 模板，公开页面保持纯净：Home、Blog、DESIGN.md、Elements。

它适合想先拥有一套完整视觉风格，再快速构建自己项目的人。模板保留了 RicoUI 的暖色画布、蓝色主色、金色强调色、编辑感标题字体、暗色模式、可复用 UI 组件，以及 MDX Blog 内容系统。

![preview](/docs/screenshot.jpeg)

## 包含内容

- Starter 首页
- MDX Blog：列表、详情页、分页、RSS、文章样式
- `/design`：把 DESIGN.md 以网页形式展示
- `/elements`：展示网站主题，包括颜色、字体、按钮、徽标、卡片、表单、布局、动效和图标
- Tailwind CSS v4 主题 token：`src/styles/global.css`
- 基于 `localStorage` 的暗色模式
- Astro Content Layer 博客配置
- SEO meta、sitemap、RSS、404 页面

## 快速开始

```bash
pnpm install
pnpm dev
```

默认开发地址是 `http://localhost:5200`。

## 优先修改

| 文件 | 用途 |
| --- | --- |
| `src/config/site.js` | 网站标题、meta、作者、仓库、社交链接 |
| `src/styles/global.css` | 主题 token、字体、颜色、容器、全局样式 |
| `docs/DESIGN.md` | 设计系统说明 |
| `src/pages/elements.astro` | 组件和主题展示 |
| `src/content/post/` | 博客文章 |

## 路由

| 路由 | 用途 |
| --- | --- |
| `/` | Starter 首页 |
| `/blog` | Blog 列表 |
| `/blog/[slug]` | Blog 文章 |
| `/design` | DESIGN.md 网页展示 |
| `/elements` | 主题和组件展示 |
| `/rss.xml` | Blog RSS |
| `/404` | 404 页面 |

## 构建

```bash
pnpm build
pnpm preview
```

部署前请在 `.env` 中设置 `PUBLIC_SITE_URL`，这样 canonical URL、sitemap 和 RSS 会使用真实域名。
