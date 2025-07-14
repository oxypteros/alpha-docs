+++
# Content Identity
title = "Recommended Posts Shortcode"
description = "Display a list of recommended posts with optional title and limit. Automatically highlights new content."

# Authoring
author = "oxypteros"
date = "2025-05-31T13:18:07+02:00"
lastmod = "2025-07-14T10:18:57+02:00"
license = "CC-BY-SA"

# Organization
categories = ["Shortcodes"]

## Series
series = "Alpha Docs"
parts = "Shortcodes"
weight = 220

# Display
featured = false
recommended = false

# Publication Control
draft = false
layout = "page"
github_edit = true

# Advanced SEO
seo_type = "TechArticle"
seo_image = "recommended-shortcode-alpha-docs-seo.png"
+++
## Example: 

{{< recommended-example TITLE="Recommended Cases" LIMIT="2" >}}

## Code
``` go-html-template
{{</* recommended TITLE="Recommended Cases" LIMIT="2" */>}} 

```

### Overview
Displays a list of recommended posts as card links with the **title**, series, category, and a pseudo-dynamic **New** badge.

### Usage
- Add `recommend = true` in the frontmatter of the content you want to highlight (to preview restart the `hugo server`).
- Use this shortcode on the **homepage** and/or **section pages** (i.e. `_index.md`).
- Posts published within **7 days from the latest site build** will show a **New** badge..

**Tip:**  If you set a `LIMIT`, the most recent recommended posts (*sorted by date*) will appear, up to that number.


### Parameters Reference
TITLE
: `TITLE="Example Title"` --- (**string**, optional) 
: H2 heading, centered above the list.

LIMIT
: `LIMIT="4"` --- (**integer**, optional)
: Maximum number of posts to display.
: Default value: `4`


#### Error Codes
liva-sc-140
: Unrecognized parameter detected.

liva-sc-141
: Invalid number or non integer value.

liva-sc-142
: No pages marked with `recommended = true`
