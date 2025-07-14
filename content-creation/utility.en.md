+++
# Content Identity
title = "Utility Pages"
description = "Alpha's Utility content guide: For minimal informational pages. Covers layout utility form, creation, and essential frontmatter like title and show_date."

# Authoring
author = "oxypteros"
date = "2025-06-03T15:38:17+02:00"
lastmod = "2025-07-14T14:27:19+02:00"
license = "CC-BY-SA"

# Organization
categories = ["Content"]

## Series
series = "Alpha Docs"
parts = "Content Creation"
weight = 460

# Display
featured = false
recommended = false

# Publication Control
draft = false
layout = "page"
github_edit = true

# Advanced SEO
seo_type = "TechArticle"
seo_image = "utility-alpha-docs-seo.png"
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
```toml
+++
# Content Identity
title = "Example utility page title"
description = ""

# Dates
date = "2006-01-02T15:04:05-07:00"
lastmod = ""
show_date = false

# Publication Control
draft = false
layout = "utility"

# Advanced SEO
seo_type = ""
seo_image = ""
twitter_username = ""
+++
```
### Reference[^1]


#### Content Identity
title 
: `title = ""` --- (**string, recommended**)
: Sets the page title and populates metadata.
: LiVa error if omitted.
: Default: Automatically filled at creation.

description 
: `description = ""` --- (**string, recommended**)
: Short description for SEO and social sharing.
: Recommended length: 50–160 characters.
: LiVa warning if omitted.

#### Dates
date
: `date = "YYYY-MM-DDTHH:MM:SSZHH:MM"` --- (**string, recommended**)
: Used for SEO metadata and page ordering. Must follow [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format.
: Hugo error if misconfigured.
: Default: Automatically set by Hugo at creation. 

lastmod 
: `lastmod = ""` --- (**string**, optional)
: Sets the last modified date. (used in metadata). 
: Use the same format as `date`.
: LiVa warning if precedes published date.

show_date
: `show_date = false` --- (**boolean**, optional)
: Display the publication date.
: Useful for **transparency** on pages like **Policy**, where versioning matters.
: Default: `false`

#### Publication Control
draft 
: `draft = false` --- (**boolean**, optional)
: Marks the page as a draft if true.
: Default: `false`.

layout 
: `layout = "utility"` --- (**string**, optional)
: Forces Hugo to use Alpha’s `utility` layout.
: LiVa warning if value is invalid.

#### Advanced SEO
seo_type
: `seo_type = "Article"` --- (**string**, optional)
: Overrides Alpha's default `@type` value in `schema.org` structured data.
: Default value: `Article`

seo_image
: `seo_image = "filename.png"` --- (**string**, optional)
: Image shown when sharing the page on social platforms. Recommended size `1200x630px`
: Place images in `assets/img/` folder. 
: Fall back to `seo_default_image` from `config/_default/params.toml` if omitted.
: LiVa warns if the file is missing or has incorrect dimensions.

twitter_username
: `twitter_username = "oxypteros"` --- (**string**, optional)
: Sets the `twitter:creator` value in Twitter cards.
: Enter the username **without** the `@` symbol.

[^1]: Only essential fields are listed: Default page fields, layout affecting options, and custom Alpha additions. See the [full list of supported frontmatter fields](https://gohugo.io/content-management/front-matter/#fields) in Hugo.