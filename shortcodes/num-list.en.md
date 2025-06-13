+++
draft = false
date = "2025-05-31T15:27:06+02:00"
lastmod = ""
layout = "page"

title = "Numbered List Shortcode"
author = "oxypteros"
license = "CC-BY-SA"
github_edit = true
series = "Alpha Docs"
  parts = "Shortcodes"
  weight = 260
categories = ["Shortcodes"]

recommended = false
featured = false
description = "Alpha's numbered list shortcode guide. Display ordered child pages using card, pill, list, or card-list styles. Ideal for chapters or ordered tutorials. Limit items shown."
# SEO
seo_type = "TechArticle"
seo_image = "num-list-shortcode-alpha-docs-seo.png"
+++
## Example:

{{< num-list-example TITLE="Analysis of Forensic Evidence" LIMIT="3">}}

## Code
```go-html-template
{{</* num-list TITLE="Analysis of Forensic Evidence" STYLE="card" LIMIT="3" */>}}
```
### Overview
A numbered list of a section child pages, offering **four different styles** and a page limit option.

### Usage
- Designed for groups of pages that must be read in a specific order, such as book chapters or tutorial steps.
- Use this shortcode on **section pages** (i.e. `_index.md`).

**Tip:** The sorting of the list is based first on `weight` and then by `date`.

### Parameters Reference
TITLE
: `TITLE="Example title"` --- (**string**, optional) 
: H2 heading.

STYLE
: `STYLE="card-list"` --- (**string**, optional) 
: Rendering style: **`card`**, **`pill`**, **`list`** or **`card-list`**. 
: Default: `card`. 

LIMIT
: `LIMIT="10"` --- (**integer**, optional)
: Maximum number of items to display.

### Error Reporting
- Warnings are printed to the Hugo terminal.
- OCD enabled.

#### Error Codes
ocd-sc-101
: Unrecognized parameter detected.

ocd-sc-100
: Invalid `STYLE` value detected.
