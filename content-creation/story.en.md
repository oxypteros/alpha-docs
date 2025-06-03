+++
draft = false
date = "2025-06-03T12:58:35+02:00"
lastmod = ""
layout = "page"

title = "Story"
author = "oxypteros"
license = "CC0"
github_edit = true
series = "Alpha Docs"
  parts = "Content Creation"
  weight = 450
categories = ["Content"]

recommended = false
featured = false
description = "Alpha theme Story layout guide. Master frontmatter for titles, dates, authors, series, taxonomies, and features like recommended & featured content."
+++
## Overview
A **story** is any Markdown file that defines `layout = "story"` in its frontmatter.

Stories mimics the simplicity of a book page, offering a minimal, immersive reading experience. They are ideal for long content like **stories**, **narratives**, and any type of **creative or reflective writing**.

## Creation
To create a story with all supported frontmatter keys:
```bash
hugo new content --kind story path/filename.md
```
Or as a **page bundle**:
```bash
hugo new content --kind story path/folder-name/index.md
```
**Note**: If you omit the `--kind story` flag, Hugo will use the default archetype that create a page with only basic frontmatter keys and you will need to manually add `layout = story`.

## Layout
The `story` layout visually differs from other Alpha layouts, yet remains consistent with Alpha's core design principles.

For best aesthetics results, it’s recommended to soft-separate layout types by section (e.g., keep stories under a `/stories/` section or similar).

Story layout supports:
- Optional decorative dropcap.
- Multipart content with series and parts.
- Display of license and copyright.
- Tags and categories.
- Allows pages to be marked as featured and recommended.

## Frontmatter
A story created with the `--kind story` flag includes the following frontmatter:
```
+++
draft = false
date = "2006-01-02T15:04:05-07:00"
lastmod = ""
layout = "story"

title = "Example page title"
author = ""
license = ""
series = ""
  parts = ""
  weight = 1000
dropcap = false
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
: `layout = "story"` --- (**string**, optional)
: Forces Hugo to use Alpha’s `story` layout.
: This is **required** to enable the layout.

title 
: `title = ""` --- (**string, recommended**)
: Sets the page title and populates metadata.
: OCD error if omitted.
: Default: Automatically filled at creation.

author 
: `author = ""` --- (**string**, optional)
: Name of the author. Used on the page and in metadata.

license 
: `license = ""` --- (**string**, optional)
: Adds a license notice for the pages content.
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

dropcap 
: `dropcap = true` --- (**boolean**, optional)
: Adds a large decorative letter to the first paragraph.
: Only applies if the first element of the content is a paragraph.
: Default: `false`

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
: OCD warning if omitted.


[^1]: Only essential fields are listed: Default page fields, layout affecting options, and custom Alpha additions. See the [full list of supported frontmatter fields](https://gohugo.io/content-management/front-matter/#fields) in Hugo.
