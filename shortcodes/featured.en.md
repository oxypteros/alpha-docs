+++
# Content Identity
title = "Featured Article Shortcode"
description = "Learn how to use the featured shortcode in the Alpha Hugo theme to display highlighted posts on your homepage or section pages. Supports multiple styles like plain, simple, and banner."

# Authoring
author = "oxypteros"
date = "2025-05-31T10:48:52+02:00"
lastmod = "2025-07-14T09:56:48+02:00"
license = "CC-BY-SA"

# Organization
categories = ["Shortcodes"]

## Series
series = "Alpha Docs"
parts = "Shortcodes"
weight = 200

# Display
featured = false
recommended = false

# Publication Control
draft = false
layout = "page"
github_edit = true

# Advanced SEO
seo_type = "TechArticle"
seo_image = "featured-shortcode-alpha-docs-seo.png"
+++
<!--more-->
## Example:
{{< featured-example TYPE="plain">}}

## Code
```go-html-template
{{</* featured TYPE="plain" */>}}
```
### Overview
Displays a featured post with a title, summary, and **Read Now** link.

### Usage
- Set `featured = true` in the frontmatter of the content page you want to feature and restart the `hugo server` to preview.
- Use this shortcode on the homepage and section pages (i.e. `_index.md`).
- The shortcode displays the page summary based on Hugo’s priority:
    1. A `<!--more-->` marker in the Markdown content.
    2. A manually defined `summary` in the front matter.
    3. An automatically generated excerpt (first `~70` words).

Alpha **recommends** using a **manually defined** frontmatter summary (`summary = ""`) for better readability, visual consistency, and SEO.

**Tip:** Only one featured post is shown at a time. If multiple posts are marked, the most recent one (*by date*) is selected.
### Parameters Reference
TYPE
: `TYPE="plain"` ---  (**string**, optional) 
: Controls the visual style of the featured section.
: TYPE values:`banner`, `simple`, `plain`(default)

#### Error Codes

liva-sc-120
: Unrecognized parameter detected.

liva-sc-121
: Invalid value detected

liva-sc-122
: No pages marked with `featured = true`
