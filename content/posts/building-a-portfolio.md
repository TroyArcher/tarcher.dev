---
title: "Building a Portfolio & Dev Blog"
date: 2025-10-12T12:30:00-05:00
draft: false
tags: ["web development", "frontend"]
categories: ["Software Engineering"]
author: "Troy Archer"
showToc: true
TocOpen: false
hidemeta: false
comments: false
description: "Key principles and strategies for building a personal portfolio and development blog."
canonicalURL: "https://tarcher.dev/posts/building-a-portfolio/"
disableHLJS: false
disableShare: false
hideSummary: false
searchHidden: false
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShowWordCount: true
ShowRssButtonInSectionTermList: true
UseHugoToc: true
---

# Building a Portfolio & Dev Blog

Software engineers benefit from personal portfolios and blogs to showcase their technical decisions, project architecture, and domain knowledge.

A resume provides a brief overview of past roles. A dedicated technical website allows engineers to document system designs, share technical lessons, and demonstrate engineering standards.

## Technical Requirements

When planning a personal website, the goal is to balance low maintenance overhead with fast page load performance.

### Site Generation Frameworks

- **Hugo**: Hugo is a static site generator written in Go. It compiles markdown files into HTML rapidly. Hugo requires zero server-side application logic and delivers strong security and speed.
- **Next.js**: A React framework offering static site generation and server-side rendering. Next.js provides flexibility for complex interactive user interfaces, but introduces higher maintenance overhead for simple content sites.
- **Tailwind CSS**: A utility-first CSS framework for custom layout styling.

Hugo was selected for this website due to its rapid build speed, low overhead, and simple deployment path. The PaperMod theme provides a minimal design with built-in dark mode support, search indexing, and syntax highlighting.

## Deployment Architecture

Static sites eliminate backend server management and database maintenance.

- **Cloudflare Pages**: Cloudflare Pages hosts static assets on a global edge network. It integrates directly with GitHub repositories to trigger automatic builds upon code pushes.
- **GitHub Pages**: An alternative static hosting platform with repository integration.

Cloudflare Pages provides automated deployment previews for pull requests, automated SSL certificate generation, and global caching.

## Conclusion

Using static site generators like Hugo combined with edge hosting via Cloudflare Pages provides a performant, low-friction platform for technical writing and architectural documentation.