+++
# Content Identity
title = "Numbered List Shortcode"
description = "Alpha's numbered list shortcode guide. Display ordered child pages using card, pill, list, or card-list styles. Ideal for chapters or ordered tutorials. Limit items shown."

# Authoring
author = "oxypteros"
date = "2025-05-31T15:27:06+02:00"
lastmod = "2025-07-14T10:39:13+02:00"
license = "CC-BY-SA"

# Organization
categories = ["Shortcodes"]

## Series
series = "Alpha Docs"
parts = "Shortcodes"
weight = 260

# Display
featured = false
recommended = false

# Publication Control
draft = false
layout = "page"
github_edit = true

# Advanced SEO
seo_type = "TechArticle"
seo_image = "num-list-shortcode-alpha-docs-seo.png"
+++
## Example:

{{< num-list-example TITLE="Analysis of Forensic Evidence" LIMIT="3">}}

## Code
```go-html-template
{{</* num_list TITLE="Analysis of Forensic Evidence" STYLE="card" LIMIT="3" */>}}
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
: Rendering style:  **`pill`**, **`list`** or **`card-list`**, **`card`** (default). 

LIMIT
: `LIMIT="10"` --- (**integer**, optional)
: Maximum number of items to display.


#### Error Codes
liva-sc-180
: Unrecognized parameter detected.

liva-sc-181
: Invalid number or non integer value.
