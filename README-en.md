# RicoUI Astro Starter

> [中文文档](README.md) | English

A design-led Astro starter template with a clean public surface: Home, Blog, DESIGN.md, and Elements.

It is built for people who want to start from a finished visual language instead of a blank page. The starter includes switchable color themes, editorial display typography, class-based dark mode, reusable UI primitives, and MDX-powered blog content.

![preview](/public/og.jpg)

![Astro](https://img.shields.io/badge/Astro-6.4.2-FF5D01?logo=astro&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-7.3.3-646CFF?logo=vite&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind-4.1.14-38B2AC?logo=tailwind-css&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-blue.svg)

> **Chinese version**: A `template-zh` branch with Chinese-translated pages and content is available. To use it:
>
> ```bash
> git checkout template-zh
> ```

## What is included

- Home page for the starter theme
- MDX Blog with list, detail pages, pagination, RSS, and article styling
- `/design` page that presents the DESIGN.md system as a website page
- `/elements` page for the website theme: colors, typography, buttons, badges, cards, forms, layout primitives, and icons
- Header theme switcher with 10 built-in color themes
- Tailwind CSS v4 base tokens in `src/styles/global.css` and theme overrides in `src/styles/themes.css`
- Dark mode with localStorage persistence
- Astro Content Layer setup for posts
- SEO metadata, sitemap, RSS feed, and custom 404 page

## Quick start

```bash
pnpm install
pnpm dev
```

The dev server runs on `http://localhost:5200` by default.

## Edit first

| File | Purpose |
| --- | --- |
| `src/config/site.js` | Site title, metadata, author, repository, social links |
| `src/config/themes.js` | Theme ids, names, swatches, source notes, and semantic token values |
| `src/styles/global.css` | Tailwind v4 base tokens, default theme, fonts, containers, global styles |
| `src/styles/themes.css` | Non-default theme variable overrides |
| `docs/DESIGN.md` | Human-readable design system notes |
| `src/pages/elements.astro` | Visual reference for the component theme |
| `src/content/post/` | Blog posts |

## Choose a theme

Use the Header theme switcher while developing to preview the site in different color directions.

| Theme | ID | Notes |
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

Configure the default theme in `src/config/themes.js`:

```js
export const themeSettings = {
	defaultThemeId: "retro-blue",
	showThemeSwitcher: true,
	persistUserSelection: true,
	storageKey: "theme_id",
	cookieName: "theme_id",
};
```

For a fixed production theme, set `defaultThemeId` to the theme you want, then set `showThemeSwitcher: false` and `persistUserSelection: false`. When persistence is enabled, the active theme is stored in `localStorage.theme_id`, mirrored to a `theme_id` cookie fallback, and applied through `<html data-theme="...">`.

Add or edit themes in `src/config/themes.js`. Keep the default `retro-blue` variables in `src/styles/global.css`, put non-default theme overrides in `src/styles/themes.css`, and create one paired DESIGN.md file per theme with both Light and Dark token sections.

## Routes

| Route | Purpose |
| --- | --- |
| `/` | Starter home |
| `/blog` | Blog list |
| `/blog/[slug]` | Blog post |
| `/design` | DESIGN.md website preview |
| `/elements` | Theme and component reference |
| `/rss.xml` | Blog RSS feed |
| `/404` | Not found page |

## Project structure

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

## Build

```bash
pnpm build
pnpm preview
```

Set `PUBLIC_SITE_URL` in `.env` before deployment so canonical URLs, sitemap, and RSS output use your real domain.

---

## Other Templates

- **SaaS Template** - Open source: [https://github.com/ricocc/ricoui-saas-template](https://github.com/ricocc/ricoui-saas-template)

- **Portfolio Template** - Open source: [https://github.com/ricocc/ricoui-portfolio](https://github.com/ricocc/ricoui-portfolio)

- **Blog Template** - Open source: [https://github.com/ricocc/public-portfolio-site](https://github.com/ricocc/public-portfolio-site)

## About the Author

I'm Rico <a href="https://x.com/ricouii" target="_blank">X (@ricouii)</a>, a web and UI designer who enjoys making interesting and creative work. I have UI/UX design experience and currently focus on web design, visual implementation, and exploring development projects.

You can add me on WeChat and say hi.

<img src="https://ricoui.com/assets/wechat.png" alt="ricocc-wechat" width="280" height="auto" style="display:inline-block;margin:12px;">

I publish updates on <a href="https://ricoui.com/" target="_blank">Rico's Blog</a>. You can also follow me on Xiaohongshu: [@Rico's Design Notes](https://www.xiaohongshu.com/user/profile/5f2b6903000000000101f51f).

---

## Support the Author

If this project is helpful, even a small amount of support is a great encouragement. Thank you!

<img src="https://ricoui.com/assets/wechat-qr.jpg" alt="ricocc-wechat" width="280" height="auto" style="display:inline-block;margin:12px;">

<br/>

<a href="https://ko-fi.com/T6T817U4KZ" target="_blank"><img height="40" src="https://storage.ko-fi.com/cdn/kofi2.png?v=6" alt="Buy Me a Coffee at ko-fi.com" /></a>

---

If this template saved you time, please consider giving it a Star.
