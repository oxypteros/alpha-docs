+++
draft = false
date = "2025-06-03T12:47:38+02:00"
lastmod = ""
layout = "page"

title = "Page"
author = "oxypteros"
license = "CC-BY-SA"
github_edit = true
series = "Alpha Docs"
  parts = "Content Creation"
  weight = 440
categories = ["Content"]

recommended = false
featured = false
description = "Alpha theme Page layout guide. Master frontmatter for titles, dates, authors, series, taxonomies, and features like recommended & featured content."
# SEO
seo_type = "TechArticle"
seo_image = "page-alpha-docs-seo.png"
+++
## Overview
A **page** is any Markdown file that:
- Is **not** an `_index.md` file.
- **Does not** specify a layout value in its frontmatter (or explicitly uses `"page"`)

This is Alpha’s default layout for content and is ideal for **articles**, **blog posts**, or **general textual content**.


## Creation
Use the following command to create a page with all supported frontmatter keys:
```bash
hugo new content --kind page [path]/[filename].md
```
Or as **page bundle**:
```bash
hugo new content --kind page [path]/[folder-name]/index.md
```
**Note**: If you omit the `--kind page` flag, Hugo will use the `default.md` archetype that create a page with only basic frontmatter keys.

## Layout
The `page` layout is Alpha’s default for standalone content.

- Supports multipart series
- Displays copyright/license
- Shows tags and categories
- Allows pages to be marked as featured and recommended.

## Frontmatter
A page created with the `--kind page` flag includes the following frontmatter:
```
+++
draft = false
date = "2006-01-02T15:04:05-07:00"
lastmod = ""
layout = "page"

title = "Example page title"
author = ""
license = ""
series = ""
  parts = ""
  weight = 1000
categories = []
tags = []

recommended = false
featured = false
description = ""
+++
```
### Reference[^1]
draft 
: `draft = false` --- (**boolean**, optional)
: Marks the page as a draft if true.
: Default: `false`.

date
: `date = "YYYY-MM-DDTHH:MM:SSZHH:MM"` --- (**string, recommended**)
: Displayed on the page and used for metadata and page ordering. Must follow [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format.
: Hugo error if misconfigured.
: Default: Automatically set by Hugo at creation. 

lastmod 
: `lastmod = ""` --- (**string**, optional)
: Sets the last modified date. Displayed on the page and used in metadata. 
: Use the same format as `date`.

layout 
: `layout = "page"` --- (**string**, optional)
: Forces Hugo to use Alpha’s `page` layout.

title 
: `title = ""` --- (**string, recommended**)
: Sets the page title and populates metadata.
: LiVa error if omitted.
: Default: Automatically filled at creation.

author 
: `author = ""` --- (**string**, optional)
: Name of the author. Used on the page and in metadata.

license 
: `license = ""` --- (**string**, optional)
: Adds a license notice for the page's content.
: Only predefined values are supported. Copyrighted content or [Creative Common licences](https://creativecommons.org/share-your-work/cclicenses/)
: Values: `copyright`, `CC0`, `CC-BY`, `CC-BY-SA`, `CC-BY-ND`,`CC-BY-NC`, `CC-BY-NC-SA`, `CC-BY-NC-ND`.

series 
: `series = ""` --- (**string**, optional)
: Marks the page as part of a series. 
: Navigation links will appear, if `weight` is defined.

parts 
: `parts = ""` --- (**string**, optional)
: Describes this page’s part in a multipart series.

weight 
: `weight = 1000` --- (**integer**, optional)
: Sets the order of the page within a series. Applies only if `series` is set.
: Default: `1000`

categories 
: `categories = []` --- (**array**, optional)
: Assigns page categories for taxonomy.
: Example: `categories = ["Docs", "Content"]`

tags 
: `tags = []` --- (**array**, optional)
: Assigns page tags for taxonomy.
: Example: `tags = ["writing", "hugo"]`

recommended
: `recommended = false` --- (**boolean**, optional)
: Mark the page as recommended content.
: Recommended content will appear after the content of pages and only at the last part of a series.
: Default: `false`

featured
: `featured = false` --- (**boolean**, optional)
: Mark the page as featured content.
: Appears in the hamburger menu and at the featured shortcode.
: Only the `featured` page with the latest date will be used.
: Default: `false`

description 
: `description = ""` --- (**string, recommended**)
: A short description for metadata.
: For best SEO, keep it between 50–160 characters.
: LiVa warning if omitted.

[^1]: Only essential fields are listed: Default page fields, layout affecting options, and custom Alpha additions. See the [full list of supported frontmatter fields](https://gohugo.io/content-management/front-matter/#fields) in Hugo.