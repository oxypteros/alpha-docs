+++
# Content Identity
title = "Homepage"
description = "Create and customize your Alpha Hugo theme homepage. Learn about _index.md setup, shortcode driven layout, and essential frontmatter options."

# Authoring
author = "oxypteros"
date = "2025-06-02T18:03:26+02:00"
lastmod = "2025-07-14T11:09:04+02:00"
license = "CC-BY-SA"

# Organization
categories = ["Content"]

## Series
series = "Alpha Docs"
parts = "Content Creation"
weight = 420

# Display
featured = false
recommended = false

# Publication Control
draft = false
layout = "page"
github_edit = true

# Advanced SEO
seo_type = "TechArticle"
seo_image = "homepage-alpha-docs-seo.png"
+++
## Overview
In most cases, you'll only need to create your homepage once. It serves as the main landing page of your website. It’s ideally the starting point where visitors can learn about your site and navigate to other sections.

## Creation
The `_index.md` file inside the `content/` folder is automatically recognized by Hugo as the homepage.
You can create it with the following command:
```bash
hugo new content --kind home _index.md
```

## Layout
Home layout is intentionally empty to give you full creative control. You’re expected to build your homepage using [Alpha's shortcodes](/docs/shortcodes "Alpha's shortcodes documentation") inside the `_index.md` file.

**Note**: The home layout is meant to be used **exclusively** with shortcodes. If you want to add plain text content, use a **text-related shortcode** to wrap it. (e.g. `text-snippet`, `text-content`)

### Recommended Homepage Structure
For a clean, informative homepage that works well as both a **landing page** and **content hub**, Alpha suggests the following structure:

1. Introduce your site with a large visual block or headline using the [Hero shortcode](/docs/shortcodes/hero/#code)  .
2. Showcase a key post directly below the hero section with the [Featured article shortcode](/docs/shortcodes/featured/#code).
3. Add a short introduction or mission statement with the [Text Snippet shortcode](/docs/shortcodes/text-snippet/#code). If you feel *wordy* use the [Text Content shortcode](/docs/shortcodes/text-content/#code)
4. Help visitors discover more content without navigating away from the homepage using the [Recommended articles shortcode ](/docs/shortcodes/recommended/#code)
5. Close the page with a prompt link to your contact page, newsletter, or another important section, by using the [Call-to-Action (CTA) shortcode ](/docs/shortcodes/cta/#code)

#### Quick Note on Layout Philosophy
Alpha’s homepage layout philosophy follows a *“do it as you like it”* approach. It’s structured but leaves everything in your hands through shortcodes:
- **Beginner-friendly:** You can copy the recommended layout as-is, and add your content.
- **Flexible for advanced users:** Rearrange, remove, customize shortcodes---or create your own. Why not?

## Frontmatter
The homepage uses the following frontmatter if it was created with `--kind home` flag.

``` toml
+++
# Content Identity
title = "Welcome to My Site"
description = ""

# Dates
date = "2006-01-02T15:04:05-07:00"
lastmod = ""

# Publication Control
draft = false
layout = "home"

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
: Populates metadata.
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

#### Publication Control
draft 
: `draft = false` --- (**boolean**, optional)
: Marks the page as a draft if true.
: Default: `false`.

layout 
: `layout = "home"` --- (**string**, optional)
: Forces Hugo to use Alpha’s `home` layout.
: LiVa warning if value is invalid.

#### Advanced SEO
seo_type
: `seo_type = "WebSite"` --- (**string**, optional)
: Overrides Alpha's default `@type` value in `schema.org` structured data.
: Default homepage value: `WebSite`

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

[^1]: Only essential fields are listed: Default page fields, layout affecting options, and custom Alpha additions. 
See the [full list of supported frontmatter fields](https://gohugo.io/content-management/front-matter/#fields) in Hugo.
