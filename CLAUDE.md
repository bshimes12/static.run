# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Is

A static site hosted at static.run. It's a collection of standalone HTML pages (self-contained with inline CSS/JS) served from the project root. `index.html` is the landing page that links to all other pages as a tile grid.

## Adding a New Page

Use the `/static.run` slash command with the HTML file path as an argument. It handles everything: updating `index.html`, committing, and pushing to GitHub.

### How index.html Works

Pages are listed as tile links inside `<div class="grid">`. New entries go directly BEFORE the `<!-- PAGES -->` comment marker. Tile format:

```html
<a href="PATH" class="tile"><span class="tile-icon">&#9670;</span><span class="tile-label">NAME</span></a>
```

## Git Workflow

- Single branch: `master`
- Remote: `origin`
- Pull with rebase before pushing: `git pull origin master --rebase`
