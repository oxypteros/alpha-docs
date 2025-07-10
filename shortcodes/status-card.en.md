+++
draft = false
date = "2025-05-31T16:26:21+02:00"
lastmod = ""
layout = "page"

title = "Status Card Shortcode"
author = "oxypteros"
license = "CC-BY-SA"
github_edit = true
series = "Alpha Docs"
  parts = "Shortcodes"
  weight = 290
categories = ["Shortcodes"]

recommended = false
featured = false
description = "Documentation for Alpha's status card shortcode. Render styled cards (info, error, warning, success) with Markdown content and optional titles."
# SEO
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
: Card types: **`error`**, **`warning`**, **`success`** or **`info`**. 
: Default value: `info`.

Inner Content 
: Main card content. Supports Markdown formatting. 

### Error Reporting
- Warnings are printed to the Hugo terminal.
- LiVa enabled.

#### Error Codes
liva-sc-131
: Unrecognized parameter detected.

liva-sc-130
: Invalid `TYPE` value detected.