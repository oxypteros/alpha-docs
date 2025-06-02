+++
draft = false
date = "2025-06-02T18:03:26+02:00"
lastmod = ""
layout = "page"

title = "Homepage"
author = "oxypteros"
license = "CC0"
github_edit = true
series = "Alpha Docs"
  parts = "Content Creation"
  weight = 420
categories = ["Content"]

recommended = false
featured = false
description = "Create and customize your Alpha Hugo theme homepage. Learn about _index.md setup, shortcode driven layout, and essential frontmatter options."
+++
## Overview
In most cases, you'll only need to create your homepage once. It serves as the main landing page of your website. It’s ideally the starting point where visitors can learn about your site and navigate to other sections.

## Creation
The `_index.md` file inside the `content/` folder is automatically recognized by Hugo as the homepage.
You can create it with the following command:
```bash
hugo new content --kind home _index.md
```
**Note**: If you run `hugo server -D` you can preview the draft demo content that ships with Alpha. 

## Layout
Home layout is intentionally empty to give you full creative control. You’re expected to build your homepage using [Alpha's shortcodes](/docs/shortcodes "Alpha's shortcodes documentation") inside the `_index.md` file.

**Note**: The home layout is meant to be used **exclusively** with shortcodes. If you want to add plain text content, use a **text-related shortcode** to wrap it. (e.g. `text-snippet`, `text-content`)

## Frontmatter
The homepage uses the following frontmatter if it was created with `--kind home` flag.
```
+++
draft = false
date = "2006-01-02T15:04:05-07:00"
lastmod = ""
layout = "home"

title = "Welcome to My Site"
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
: `layout = "home"` --- (**string**, optional)
: Forces Hugo to use Alpha’s `home` layout.

title 
: `title = ""` --- (**string, recommended**)
: Populates metadata.
: OCD error if omitted.
: Default: Automatically filled at creation. If omitted, the site title is used.

description 
: `description = ""` --- (**string, recommended**)
: A short description for metadata.
: For best SEO, keep it between 50–160 characters.
: OCD warning if omitted.
: Default: empty.

[^1]: Only essential fields are listed: Default page fields, layout affecting options, and custom Alpha additions. 
See the [full list of supported frontmatter fields](https://gohugo.io/content-management/front-matter/#fields) in Hugo.
