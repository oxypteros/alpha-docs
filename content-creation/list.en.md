+++
draft = false
date = "2025-06-02T18:21:53+02:00"
lastmod = ""
layout = "page"

title = "List Page (Section)"
author = "oxypteros"
license = "CC-BY-SA"
github_edit = true
series = "Alpha Docs"
  parts = "Content Creation"
  weight = 430
categories = ["Content"]

recommended = true
featured = false
description = "Learn to create section landing pages (list pages) in Alpha Hugo theme. Covers _index.md setup, pagination, shortcode customization, and frontmatter."
# SEO
seo_type = "TechArticle"
seo_image = "list-alpha-docs-seo.png"
+++
## Overview
The **list** (or section) page is an `_index.md` file that serves as the landing page for a content section. It displays a **paginated list** of the pages inside that section. 

A section is any folder within the `content/` directory that contains **content pages** or **page bundles**.

In Alpha, a list page can also act as a transitional landing page between different parts of a series. This is particularly useful when the previous part exists **outside** the section and the next part is a **child within it** or when one series ends and another begins.

**Note**: Don’t confuse a section list page with the `_index.md` in the **root** of the `content/` folder ([homepage](/docs/content-creation/homepage/)).

## Creation
A list page is automatically recognized by Hugo when an `_index.md` file exists inside a subfolder of `content/`.

To create one, use:
```bash
hugo new content --kind list [section-folder]/_index.md
```
 **Note**: If you run `hugo server -D` you can preview the draft demo list page (`content/blog/_index.md`) that ships with Alpha. 

## Layout
Alpha’s `list` layout renders a minimal page that includes the **section title** and a **paginated list** of its child page and sub-sections, below the content of the `_index.md`.

You can personalize a list page by adding [Alpha's shortcodes](/docs/shortcodes/ "Alpha's shortcodes documentation") inside the `_index.md` files.

**Note**: The list layout is meant to be used **exclusively** with shortcodes or left empty. If you need to add **plain text** content, use a **text related shortcode** to wrap it.

## Frontmatter
List pages uses the following frontmatter
```
+++
draft = false
date = "2006-01-02T15:04:05-07:00"
lastmod = ""
layout = "list"
paginate = true

title = "Example list title"
series = ""
weight = 1000
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
: Used for SEO metadata and page ordering. Must follow [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format.
: Hugo error if misconfigured.
: Default: Automatically set by Hugo at creation. 

lastmod 
: `lastmod = ""` --- (**string**, optional)
: Sets the last modified date. (used in metadata). 
: Use the same format as `date`.

layout 
: `layout = "list"` --- (**string**, optional)
: Forces Hugo to use Alpha’s `list` layout.

paginate 
: `paginate = true` --- (**boolean**, optional)
: Renders a paginated list of **regular pages** and any **list pages** from sub-sections, appearing *after* any content in the `_index.md` file.
: To change how many posts show per page, edit the `pagerSize` value in `config/_default/hugo.toml`. 
Default: `true`

title 
: `title = ""` --- (**string, recommended**)
: Sets the page title and populates metadata.
: LiVa error if omitted.
: Default: Automatically filled at creation.

series 
: `series = ""` --- (**string**, optional)
: Marks the page as part of a series. 
: Navigation links will not appear, but it can function as a transition or gateway page.

weight 
: `weight = 1000` --- (**integer**, optional)
: Sets the order of the page within a series. Applies only if `series` is set.
: Default: `1000`

description 
: `description = ""` --- (**string, recommended**)
: A short description for metadata.
: For best SEO, keep it between 50–160 characters.
: LiVa warning if omitted.


[^1]: Only essential fields are listed: Default page fields, layout affecting options, and custom Alpha additions. See the [full list of supported frontmatter fields](https://gohugo.io/content-management/front-matter/#fields) in Hugo.