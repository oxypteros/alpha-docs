+++
# Content Identity
title = "Search"
description = "Add search to your Alpha site using Pagefind. Guide covers enabling the feature, build commands for deployment (Netlify, Vercel, Cloudflare) and local use."

# Authoring
author = "oxypteros"
date = "2025-06-04T11:50:40+02:00"
license = "CC-BY-SA"

# Organization
categories = ["Integrations"]

## Series
series = "Alpha Docs"
parts = "Integrations"
weight = 550

# Display
featured = false
recommended = false

# Publication Control
draft = false
layout = "page"
github_edit = true

# Advanced SEO
seo_type = "TechArticle"
seo_image = "search-alpha-docs-seo.png"
+++
Alpha's search functionality is powered by Pagefind. You can learn more about it on the [official website](https://pagefind.app/ "Pagefind website") or experience it directly by using the search feature on this site.

## Enable Search
To enable search, (disabled by default):
1. Set `pagefind_enabled = true` in `config/_default/params.toml`. 
(This enables the search button and Alpha's JavaScript required for the search functionality.)
2. Add **Pagefind** to your build.

### Add Pagefind to Your Build
Integrate Pagefind directly into your build command to simplify setup.

If you deploy your site using services like **Vercel**, **Netlify**, or **Cloudflare Pages**, update your **build command** in the respective platform settings to:
```bash
hugo --gc --minify && npx pagefind --site "public"
```
This command builds your Hugo site, then runs Pagefind to generate the searchable index.

You can find platform specific instructions in the [Deployment documentation](/docs/deployment/) pages.

If you’re building your site **locally** or testing search before deployment, run the same command in your terminal:
```bash
hugo --gc --minify && npx pagefind --site "public"
```
**Note**: You must have Node.js installed on your local system.

### How it works
Pagefind is installed in Hugo’s `public/` folder (Hugo's default output directory). It scans the generated HTML and builds a lightweight search index from your site’s content.
- Every time you build your site with the above command, Pagefind updates the search index automatically.
- New content will only appear in search **after** you rebuild your site with the above command.

In essence, Pagefind is a static search library, just like Hugo is a static site generator. 
The same principles apply: You must **build** to **update**!.
