# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a personal blog built with Astro using the Storyteller theme. The blog supports Korean content with multilingual labels and is configured to deploy to GitHub Pages at `https://flameware.github.io/blog`.

## Development Commands

- `bun dev` - Start development server
- `bun run build` - Build for production
- `bun run preview` - Preview production build
- `bun run astro` - Run Astro CLI commands

## Architecture

### Content Management
- Blog posts are stored in `src/content/article/` as MDX files
- Content schema is defined in `src/content/config.ts` with required fields:
  - `title`, `description`, `pubDate`, `category`, `tags`
  - Optional: `author` (defaults to "Seongki Sohn"), `featured`, `thumb`, `large`

### Site Configuration
- Main configuration in `src/site.config.mjs` controls:
  - Site titles and labels (Korean text)
  - Display options for homepage, posts, pagination
  - Author and footer link settings
- Astro configuration in `astro.config.mjs` sets up:
  - Tailwind CSS integration via Vite
  - MDX support
  - GitHub Pages deployment settings (base: '/blog')

### File Structure
- `src/components/` - Reusable Astro components (Header, Footer, PostCard, etc.)
- `src/layouts/` - Page layouts (BlogLayout.astro)
- `src/pages/` - Route pages with dynamic routing for articles, categories, tags, authors
- `src/styles/global.css` - Global styles
- `public/` - Static assets including theme toggle script

### Styling
- Uses Tailwind CSS v4 with Typography plugin
- Global styles in `src/styles/global.css`
- Theme toggle functionality via `public/scripts/theme-toggle.js`

## Content Creation

Blog posts should be created in `src/content/article/` with filename format: `YYYY-MM-DD-title.mdx`

Required frontmatter:
```yaml
title: "Post Title"
description: "Post description"
pubDate: 2025-08-05
category: "Category Name"
tags: ["tag1", "tag2"]
```