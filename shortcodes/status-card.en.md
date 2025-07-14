+++
# Content Identity
title = "Status Card Shortcode"
description = "Documentation for Alpha's status card shortcode. Render styled cards (info, error, warning, success) with Markdown content and optional titles."

# Authoring
author = "oxypteros"
date = "2025-05-31T16:26:21+02:00"
lastmod = "2025-07-14T10:49:05+02:00"
license = "CC-BY-SA"

# Organization
categories = ["Shortcodes"]

## Series
series = "Alpha Docs"
parts = "Shortcodes"
weight = 290

# Display
featured = false
recommended = false

# Publication Control
draft = false
layout = "page"
github_edit = true

# Advanced SEO
seo_type = "TechArticle"
seo_image = "status-card-shortcode-alpha-docs-seo.png"
+++
## Example

{{< status-card-example TITLE="Investigation Status" TYPE="info">}}

**Current Status**: Cold Case - *Inactive*
**Lead Agency:** Los Santos Police Department
**Last Known Action:** Case review requested (2020) - *No new leads identified*.
**Contact for Tips:** Los Santos PD Cold Case Unit (**555-1234**)

{{< /status-card-example >}}

## Code
``` go-html-template
{{</* status_card TITLE="Investigation Status" TYPE="info" */>}}

**Current Status**: Cold Case - *Inactive*
**Lead Agency:** Los Santos Police Department
**Last Known Action:** Case review requested (2020) - *No new leads identified*.
**Contact for Tips:** Los Santos PD Cold Case Unit (**555-1234**)

{{</* /status_card */>}}
```
### Overview
A closed shortcode that renders an `info`, `error`, `warning`, or `success` card with an optional title and markdown styled text content.

### Usage
- Intended for inserting an informative status card related to the content.
- This shortcode **requires** both opening and closing tags.

### Parameters Reference
TITLE 
: `TITLE="Example title"` --- (**string**, optional) 
: H2 heading. 

TYPE
: `TYPE="error"` --- (**string**, optional) 
: Card types: **`error`**, **`warning`**, **`success`**, **`info`** (default). 

Inner Content 
: Main card content. Supports Markdown formatting. 


#### Error Codes
liva-sc-210
: Unrecognized parameter detected.

liva-sc-211
: Invalid value detected.