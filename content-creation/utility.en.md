+++
draft = false
date = "2025-06-03T15:38:17+02:00"
lastmod = ""
layout = "page"

title = "Utility Pages"
author = "oxypteros"
license = "CC0"
github_edit = true
series = "Alpha Docs"
  parts = "Content Creation"
  weight = 460
categories = ["Content"]

recommended = false
featured = false
description = "Alpha's Utility content guide: For minimal informational pages. Covers layout utility form, creation, and essential frontmatter like title and show_date."
+++
## Overview
An `utility` page is any Markdown file (`.md`) that has `layout = utility` in the frontmatter.

This layout is specifically created for pages like **About**, **Policy**, **Contact**, and other administrative or informational pages.

Its purpose is to make *"utility pages"* feel almost *hardcoded*, fully integrated into the theme while remaining completely manageable through content files.

## Creation
Create a `utility` page with all supported frontmatter using:
```bash
hugo new content --kind utility [path]/[filename].md
```
Or as a **page bundle**:
```bash
hugo new content --kind utility [path]/[folder-name]/index.md
```
**Note**: If you omit the `--kind utility` flag, Hugo will use the `default.md` archetype that create a page with only basic frontmatter and you will need to manually add `layout = utility`.

## Layout
The `utility` layout is a stripped down variant of the `page` layout, designed for maximum simplicity.

Its main goal is to create a subtle visual distinction between *"utility pages"* and regular content.

## Frontmatter
A page created with the `--kind utility` flag includes the following frontmatter:
```
+++
draft = false
date = "2006-01-02T15:04:05-07:00"
lastmod = ""
layout = "utility"
show_date = false

title = "Example page title"

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
: `layout = "utility"` --- (**string**, optional)
: Forces Hugo to use Alpha’s `utility` layout.
: This is **required** to enable the layout.

show_date
: `show_date = false` --- (**boolean**, optional)
: Display the publication date.
: Useful for **transparency** on pages like **Policy**, where versioning matters.
: Default: `false`

title 
: `title = ""` --- (**string, recommended**)
: Sets the page title and populates metadata.
: OCD error if omitted.
: Default: Automatically filled at creation.

description 
: `description = ""` --- (**string, recommended**)
: A short description for metadata.
: For best SEO, keep it between 50–160 characters.
: OCD warning if omitted.


[^1]: Only essential fields are listed: Default page fields, layout affecting options, and custom Alpha additions. See the [full list of supported frontmatter fields](https://gohugo.io/content-management/front-matter/#fields) in Hugo.