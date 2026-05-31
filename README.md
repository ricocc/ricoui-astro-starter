# RicoUI Astro Starter

A design-led Astro starter template with a clean public surface: Home, Blog, DESIGN.md, and Elements.

It is built for people who want to start from a finished visual language instead of a blank page. The starter includes switchable color themes, editorial display typography, class-based dark mode, reusable UI primitives, and MDX-powered blog content.

![preview](/docs/screenshot.jpeg)

![Astro](https://img.shields.io/badge/Astro-6.4.2-FF5D01?logo=astro&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-7.3.3-646CFF?logo=vite&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind-4.1.14-38B2AC?logo=tailwind-css&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-blue.svg)

## What is included

- Home page for the starter theme
- MDX Blog with list, detail pages, pagination, RSS, and article styling
- `/design` page that presents the DESIGN.md system as a website page
- `/elements` page for the website theme: colors, typography, buttons, badges, cards, forms, layout primitives, and icons
- Header theme switcher with `Retro Blue`, `Minimal Mono`, and `Forest Green`
- Tailwind CSS v4 tokens in `src/styles/global.css`
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
| `src/styles/global.css` | Theme tokens, fonts, colors, containers, global styles |
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

For a fixed production theme, set `defaultThemeId` to the theme you want, then set `showThemeSwitcher: false` and `persistUserSelection: false`. When persistence is enabled, the active theme is stored in `localStorage.theme_id`, mirrored to a `theme_id` cookie fallback, and applied through `<html data-theme="...">`. Add or edit themes in `src/config/themes.js`, mirror the CSS variable overrides in `src/styles/global.css`, and create one paired DESIGN.md file per theme with both Light and Dark token sections.

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
    article.css
```

## Build

```bash
pnpm build
pnpm preview
```

Set `PUBLIC_SITE_URL` in `.env` before deployment so canonical URLs, sitemap, and RSS output use your real domain.
