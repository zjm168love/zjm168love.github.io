# Pep's Notes

个人博客：后端工程、分布式系统与 AI Agent 实践。

线上地址：<https://zjm168love.github.io>

技术栈：[Astro](https://astro.build/)（官方 blog 模板）+ GitHub Actions 自动部署到 GitHub Pages。

## 写新文章

在 `src/content/blog/` 下新建一个 Markdown 文件（文件名即 URL slug），frontmatter 必填 `title` / `description` / `pubDate`：

```markdown
---
title: '文章标题'
description: '一句话摘要，会显示在列表页和搜索结果里'
pubDate: '2026-11-11'
---

正文……
```

可选字段：`updatedDate`（更新日期）、`heroImage`（题图，引用 `src/assets/` 下的图片）。

推送到 `master` 后，GitHub Actions 自动构建并发布，无需手动部署。

## 本地开发

要求 Node ≥ 22.23.4。

```bash
npm install
npm run dev      # 本地预览 http://localhost:4321
npm run build    # 构建，产物在 dist/
```

## 站点配置

- 站点标题 / 简介：`src/consts.ts`
- 域名 / 集成 / 字体：`astro.config.mjs`
- 导航 / 页脚：`src/components/Header.astro`、`src/components/Footer.astro`
- 全局样式：`src/styles/global.css`
- 部署工作流：`.github/workflows/deploy.yml`