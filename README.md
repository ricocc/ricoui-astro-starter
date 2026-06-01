# RicoUI Astro 启动模板

> [English](README-en.md) | 中文文档

一个设计驱动的 Astro 启动模板，公开页面保持纯净：首页、博客、设计文档和组件库。

它适合想先拥有一套完整视觉风格，再快速构建自己项目的人。模板包含可切换的颜色主题、思源黑体展示字体、基于 class 的暗色模式、可复用 UI 组件和 MDX 博客内容系统。

![preview](/docs/screenshot.jpeg)

![Astro](https://img.shields.io/badge/Astro-6.4.2-FF5D01?logo=astro&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-7.3.3-646CFF?logo=vite&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind-4.1.14-38B2AC?logo=tailwind-css&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-blue.svg)

## 包含内容

- 启动模板首页
- MDX 博客：列表、详情页、分页、RSS、文章样式
- `/design`：设计文档和主题系统以网页形式展示
- `/elements`：网站主题组件库，包括颜色、字体、按钮、徽章、卡片、表单、布局和图标
- Header 主题切换器，内置 10 种颜色主题
- Tailwind CSS v4 基础令牌在 `src/styles/global.css`，主题覆盖在 `src/styles/themes.css`
- 基于 localStorage 的暗色模式
- Astro Content Layer 博客配置
- SEO 元数据、站点地图、RSS 和自定义 404 页面

## 快速开始

```bash
pnpm install
pnpm dev
```

默认开发地址是 `http://localhost:5200`。

## 优先修改

| 文件 | 用途 |
| --- | --- |
| `src/config/site.js` | 网站标题、元数据、作者、仓库、社交链接 |
| `src/config/themes.js` | 主题 id、名称、色板、来源说明和语义令牌 |
| `src/styles/global.css` | Tailwind v4 基础令牌、默认主题、字体、容器、全局样式 |
| `src/styles/themes.css` | 非默认主题变量覆盖 |
| `docs/DESIGN.md` | 设计系统说明文档 |
| `src/pages/elements.astro` | 组件和主题展示页面 |
| `src/content/post/` | 博客文章 |

## 选择主题

开发时可以使用 Header 里的主题切换器预览不同色彩方向。

| 主题 | ID | 说明 |
| --- | --- | --- |
| Retro Blue | `retro-blue` | `docs/DESIGN/retro-blue.md` |
| Minimal Mono | `minimal-mono` | `docs/DESIGN/minimal-mono.md` |
| Forest Green | `forest-green` | `docs/DESIGN/forest-green.md` |
| Claude | `claude` | `docs/DESIGN/claude.md` |
| Creator Yellow | `creator-yellow` | `docs/DESIGN/creator-yellow.md` |
| Precision Orange | `precision-orange` | `docs/DESIGN/precision-orange.md` |
| Comic Pulp | `comic-pulp` | `docs/DESIGN/comic-pulp.md` |
| Midnight Pastel | `midnight-pastel` | `docs/DESIGN/midnight-pastel.md` |
| Sky Blue | `sky-blue` | `docs/DESIGN/sky-blue.md` |
| Rico Red | `rico-red` | `docs/DESIGN/rico-red.md` |

默认主题在 `src/config/themes.js` 里配置：

```js
export const themeSettings = {
	defaultThemeId: "retro-blue",
	showThemeSwitcher: true,
	persistUserSelection: true,
	storageKey: "theme_id",
	cookieName: "theme_id",
};
```

如果要做成固定主题的生产项目，把 `defaultThemeId` 改成你想要的主题，然后设置 `showThemeSwitcher: false` 和 `persistUserSelection: false`。开启持久化时，当前主题保存在 `localStorage.theme_id`，同步到 `theme_id` cookie 作为兜底，通过 `<html data-theme="...">` 应用。

新增主题时，先在 `src/config/themes.js` 中添加，默认 `retro-blue` 变量保留在 `src/styles/global.css`，非默认主题覆盖放在 `src/styles/themes.css`，每个主题配一份 DESIGN.md 文件，包含亮色和暗色令牌两节。

## 路由

| 路由 | 用途 |
| --- | --- |
| `/` | 首页 |
| `/blog` | 博客列表 |
| `/blog/[slug]` | 博客文章 |
| `/design` | 设计文档和主题系统展示 |
| `/elements` | 主题和组件展示 |
| `/rss.xml` | 博客 RSS |
| `/404` | 404 页面 |

## 项目结构

```txt
docs/
  DESIGN/
    retro-blue.md
    minimal-mono.md
    forest-green.md
    ...
  DESIGN.md
public/
  assets/
  favicon.png
  og.jpg
src/
  components/
  config/site.js
  content/post/
  layouts/
  pages/
    blog/
    index.astro
    design.astro
    elements.astro
    404.astro
    rss.xml.js
  styles/
    global.css
    themes.css
    article.css
```

## 构建

```bash
pnpm build
pnpm preview
```

部署前请在 `.env` 中设置 `PUBLIC_SITE_URL`，这样 canonical URL、sitemap 和 RSS 会使用真实域名。

---

## 其他模板

- **SaaS Template** - 开源：[https://github.com/ricocc/ricoui-saas-template](https://github.com/ricocc/ricoui-saas-template)
- **Portfolio Template** - 开源：[https://github.com/ricocc/ricoui-portfolio](https://github.com/ricocc/ricoui-portfolio)
- **Blog Template** - 开源：[https://github.com/ricocc/public-portfolio-site](https://github.com/ricocc/public-portfolio-site)

## 关于作者

我是 Rico <a href="https://x.com/ricouii" target="_blank">X (@ricouii)</a>，网页/UI 设计师，热衷于做有趣和创意的作品。拥有 UI/UX 设计工作经验，目前专注于网页设计、视觉落地和开发项目探索。

可以添加我的微信，交个朋友。

<img src="https://ricoui.com/assets/wechat.png" alt="ricocc-wechat" width="280" height="auto" style="display:inline-block;margin:12px;">

我平时在博客 <a href="https://ricoui.com/" target="_blank">Rico's Blog</a> 更新内容。也可以关注我的小红书 [@Rico的设计漫想](https://www.xiaohongshu.com/user/profile/5f2b6903000000000101f51f)。

---

## 💜 支持作者

如果觉得有所帮助的话，一点点支持就可以大大激励创作者的热情，感谢！

<img src="https://ricoui.com/assets/wechat-qr.jpg" alt="ricocc-wechat" width="280" height="auto" style="display:inline-block;margin:12px;">

<br/>

<a href="https://ko-fi.com/T6T817U4KZ" target="_blank"><img height="40" src="https://storage.ko-fi.com/cdn/kofi2.png?v=6" alt="Buy Me a Coffee at ko-fi.com" /></a>

---

⭐ 如果这个模板帮你节省了时间，请点一个 Star。
