+++
draft = false
date = "2025-05-30T18:00:55+02:00"
lastmod = ""
layout = "page"

title = "Content Organization"
author = "oxypteros"
license = "CC0"
series = "Alpha Docs"
  parts = "Content Structure"
  weight = 180
categories = ["Content"]

recommended = false
featured = false
description = "Learn Alpha's recommended content organization. Understand sections, page bundles (required for images), _index.md, index.md, and file structure."
+++
{{< text-snippet TITLE="Alpha & Content">}}
Alpha recommends a **specific way** of organizing content. It doesn’t deviate from Hugo’s defaults, but it is slightly opinionated. Everything starts with the **content folder**.
{{< /text-snippet>}}
## Overview
All content related files and folders are placed inside the `content/` folder. For all intents and purposes, this folder serves as the **root** for your site’s content.

Subfolders inside `content/` fall into two categories:
1. [Sections](#sections)
2. [Page Bundles](#page-bundles)

Files inside `content/` can be:
1. [Markdown files](#markdown-files)
2. [Other files](#other-files)

## Section Folders
Every **subfolder** inside `content/` that contains a `_index.md` file is considered a **section** by Hugo.

Sections are used to group related pages under a common path and layout. The folder name becomes part of the section's URL.

For example, consider the following structure for a site deployed at `example.com`:

```bash
content 
├── articles/
│   └── _index.md
└── _index.md
```
- Navigating to `example.com` loads the homepage rendered by the root `_index.md` using the **home layout**.
- Visiting `example.com/articles/` loads the section page rendered by `articles/_index.md` using the **list layout**.

## Page Bundles
Any folder inside `content/` that contains an `index.md` file is treated as a **page bundle**.

Page bundles allow you to keep all page specific resources (like images) alongside the page content in the same folder. Ideal for keeping things tidy.

With Alpha, if you want to add images to a post, you **must use a page bundle**. 

Expanding the previous example:
```bash
content 
├── articles/
│   ├── first-article/
│   │   ├── image.jpg
│   │   └── index.md
│   └── _index.md
└── _index.md
```
- Navigating to `example.com/articles/first-article/` renders the page using `index.md` and the **page layout**.
- `image.jpg` is accessible only within `first-article/`, keeping page resources organized and scoped to their specific content.

## Markdown Files
Markdown files provide the actual content of your pages. What’s rendered depends on:
- The [**frontmatter**](/docs/content-creation)
- The [**shortcodes**](/docs/shortcodes) used
- Your **text**

_index.md (root) 
: Defines the homepage content. 
: In Alpha, the homepage is intentionally empty. You populate it with shortcodes and content manually.

_index.md (section)
: Defines the content and appearance of a section landing page. 
: Lists all pages and bundles inside that section.

index.md 
: Must be inside a folder (which becomes the page bundle). It defines a content page (e.g. post, story, project page).
: The folder name becomes the URL path
: Can include resources, like images

custom-name.md
: Create content pages (posts, articles etc.) 
: Can be placed everywhere inside the `content/`, except inside a page bundle.
: The file name becomes the URL path
: Cannot include resources like images

Final example:
```bash
content 
├── articles/
│   ├── first-article/
│   │   ├── image.jpg
│   │   └── index.md
│   ├── second-article.md  
│   └── _index.md
├── policy.md
└── _index.md
```
- `first-article/` is a page bundle. URL: `/articles/first-article/`
- `second-article.md` is a single file. URL: `/articles/second-article/`
- `policy.md` is a single file. URL: /policy/
- Only `first-article/` can use `image.jpg` as a page resource.

## Other files
Hugo supports many file types, but Alpha officially supports:
- Markdown files for content
- Images (within page bundles only)

Future versions will support additional resource types (e.g., video, audio), but Alpha’s focus will always remain on **textual content**.
