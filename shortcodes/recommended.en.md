+++
draft = false
date = "2025-05-31T13:18:07+02:00"
lastmod = ""
layout = "page"

title = "Recommended Posts Shortcode"
author = "oxypteros"
license = "CC-BY-SA"
github_edit = true
series = "Alpha Docs"
  parts = "Shortcodes"
  weight = 220
categories = ["Shortcodes"]

recommended = false
featured = false
description = "Display a list of recommended posts with optional title and limit. Automatically highlights new content."
# SEO
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
- Add `recommend = true` in the frontmatter of the content you want to highlight.
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

### Error Reporting
- Warnings are printed to the Hugo terminal.
- LiVa enabled.

#### Error Codes
liva-sc-181
: Unrecognized parameter detected.

liva-sc-182
: Invalid number or non integer value.

liva-sc-183
: No pages marked with `recommended = true`
