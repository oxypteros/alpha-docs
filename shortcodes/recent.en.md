+++
# Content Identity
title = "Recent Posts Shortcode"
description = "Display a list of recent posts with optional title and limit. Automatically highlights new content."

# Authoring
author = "oxypteros"
date = "2025-05-31T14:50:40+02:00"
lastmod = "2025-07-14T10:25:28+02:00"
license = "CC-BY-SA"

# Organization
categories = ["Shortcodes"]

## Series
series = "Alpha Docs"
parts = "Shortcodes"
weight = 240

# Display
featured = false
recommended = false

# Publication Control
draft = false
layout = "page"
github_edit = true

# Advanced SEO
seo_type = "TechArticle"
seo_image = "recent-shortcode-alpha-docs-seo.png"
+++
## Example: 

{{< recent-example TITLE="Recent Cases" LIMIT="3" >}}

## Code
``` go-html-template
{{</* recent TITLE="Recent Cases" LIMIT="3" */>}} 

```

### Overview
Displays a list of the recent posts as card links with the **title**, series, category, and a pseudo-dynamic **New** badge.

### Usage
- Use this shortcode on the **homepage** and/or **section pages** (i.e. `_index.md`).
- Posts published within **7 days from the latest site build** will display a **New** badge.

**Tip:**  If you set a `LIMIT`, the most recent posts (*sorted by date*) will appear, up to that number.


### Parameters Reference
TITLE
: `TITLE="Example Title"` --- (**string**, optional) 
: H2 heading.

LIMIT
: `LIMIT="4"` --- (**integer**, optional)
: Maximum number of posts to display.
: Default value: `4`

#### Error Codes
liva-sc-160
: Unrecognized parameter detected.

liva-sc-161
: Invalid number or non integer value.
