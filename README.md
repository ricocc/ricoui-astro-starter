# RicoUI Astro Starter

A design-led Astro starter template with a clean public surface: Home, Blog, DESIGN.md, and Elements.

It is built for people who want to start from a finished visual language instead of a blank page. The theme includes warm light surfaces, a blue primary accent, a gold highlight color, editorial display typography, class-based dark mode, reusable UI primitives, and MDX-powered blog content.

![preview](/docs/screenshot.jpeg)

![Astro](https://img.shields.io/badge/Astro-6.4.2-FF5D01?logo=astro&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-7.3.3-646CFF?logo=vite&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind-4.1.14-38B2AC?logo=tailwind-css&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-blue.svg)

## What is included

- Home page for the starter theme
- MDX Blog with list, detail pages, pagination, RSS, and article styling
- `/design` page that presents the DESIGN.md system as a website page
- `/elements` page for the website theme: colors, typography, buttons, badges, cards, forms, layout primitives, motion, and icons
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
| `src/styles/global.css` | Theme tokens, fonts, colors, containers, global styles |
| `docs/DESIGN.md` | Human-readable design system notes |
| `src/pages/elements.astro` | Visual reference for the component theme |
| `src/content/post/` | Blog posts |

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
  DESIGN.md
  DESIGN-PREVIEW.html
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
