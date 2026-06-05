# RicoUI Astro Starter

> [English](README-en.md)  | 中文文档


一个以设计为驱动的 Astro starter 模板，公开页面保持纯净：Home、Blog、DESIGN.md、Elements。

它适合想先拥有一套完整视觉风格，再快速构建自己项目的人。模板保留了 RicoUI 的编辑感标题字体、暗色模式、可复用 UI 组件、MDX Blog 内容系统，并加入了多主题色切换。

![preview](/public/og.jpg)

> **中文版本**：本仓库另有一个 `template-zh` 分支，页面文案和内容已针对中文字体进行了优化。如需中文版本，可切换到该分支：
>
> ```bash
> git checkout template-zh
> ```

## 包含内容

- Starter 首页
- MDX Blog：列表、详情页、分页、RSS、文章样式
- `/design`：把 DESIGN.md 和主题系统以网页形式展示
- `/elements`：展示网站主题，包括颜色、字体、按钮、徽标、卡片、表单、布局、动效和图标
- Header 主题切换：`Retro Blue`、`Minimal Mono`、`Forest Green`
- Tailwind CSS v4 主题 token：`src/styles/global.css`
- 基于 `localStorage` 的主题选择和暗色模式
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
| `src/config/themes.js` | 主题 id、名称、色板、来源说明和语义 token |
| `src/styles/global.css` | 主题 token、字体、颜色、容器、全局样式 |
| `docs/DESIGN.md` | 设计系统说明 |
| `src/pages/elements.astro` | 组件和主题展示 |
| `src/content/post/` | 博客文章 |

## 选择主题开发

开发时可以使用 Header 里的主题切换器预览不同色彩方向。

| 主题 | ID | 说明 |
| --- | --- | --- |
| Retro Blue | `retro-blue` | `docs/DESIGN/retro-blue.md` |
| Minimal Mono | `minimal-mono` | `docs/DESIGN/minimal-mono.md` |
| Forest Green | `forest-green` | `docs/DESIGN/forest-green.md` |

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

如果要做成固定主题的生产项目，把 `defaultThemeId` 改成你想要的主题，然后设置 `showThemeSwitcher: false` 和 `persistUserSelection: false`。这样用户不会看到主题切换器，也不会被旧的 `localStorage` 选择覆盖。开启持久化时，当前主题保存在 `localStorage.theme_id`，并同步到 `theme_id` cookie 作为兜底，然后通过 `<html data-theme="...">` 应用到全站。如果要新增主题，先修改 `src/config/themes.js`，再在 `src/styles/global.css` 中补齐对应 CSS 变量覆盖，并为这个主题新增一份 DESIGN.md。

建议每个主题只建一份 DESIGN.md，在同一个文件里分成 `Light Tokens` 和 `Dark Tokens` 两节。不要把亮色和暗色拆成两个文件，这样后续主题多了以后更容易维护。

## 路由

| 路由 | 用途 |
| --- | --- |
| `/` | Starter 首页 |
| `/blog` | Blog 列表 |
| `/blog/[slug]` | Blog 文章 |
| `/design` | DESIGN.md 和主题系统展示 |
| `/elements` | 主题和组件展示 |
| `/rss.xml` | Blog RSS |
| `/404` | 404 页面 |

## 构建

```bash
pnpm build
pnpm preview
```

部署前请在 `.env` 中设置 `PUBLIC_SITE_URL`，这样 canonical URL、sitemap 和 RSS 会使用真实域名。


---

## 其他模板

-  **SaaS Template** - 开源 :  [https://github.com/ricocc/ricoui-saas-template](https://github.com/ricocc/ricoui-saas-template)

-  **Portfolio Template** - 开源 :  [https://github.com/ricocc/ricoui-portfolio](https://github.com/ricocc/ricoui-portfolio)

-  **Blog Template** - 开源 :  [https://github.com/ricocc/public-portfolio-site](https://github.com/ricocc/public-portfolio-site)





## 关于作者

我是Rico <a href="https://x.com/ricouii" target="_blank">X (@ricouii)</a>，网页/UI设计师，热衷于做些有趣和创意的作品。拥有 UI/UX 设计工作经验，目前专注于网页设计和视觉落地，以及开发项目探索。

可以添加我的微信，交个朋友

<img src="https://ricoui.com/assets/wechat.png" alt="ricocc-wechat" width="280" height="auto" style="display:inline-block;margin:12px;">


我平时在博客 <a href="https://ricoui.com/" target="_blank">Rico's Blog</a> 更新内容。也可以关注我的小红书 [@Rico的设计漫想](https://www.xiaohongshu.com/user/profile/5f2b6903000000000101f51f).

---

## 💜 支持作者

如果觉得有所帮助的话，一点点支持就可以大大激励创作者的热情，感谢！

<img src="https://ricoui.com/assets/wechat-qr.jpg" alt="ricocc-wechat" width="280" height="auto" style="display:inline-block;margin:12px;">


<br/>

<a href="https://ko-fi.com/T6T817U4KZ" target="_blank"><img height="40" src="https://storage.ko-fi.com/cdn/kofi2.png?v=6" alt="Buy Me a Coffee at ko-fi.com" /></a>

---


⭐ 如果这个模板帮你节省了时间，请点一个 Star。
