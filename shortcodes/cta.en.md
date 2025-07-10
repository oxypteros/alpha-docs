+++
draft = false
date = "2025-05-31T15:13:33+02:00"
lastmod = ""
layout = "page"

title = "Call to Action Shortcode"
author = "oxypteros"
license = "CC-BY-SA"
github_edit = true
series = "Alpha Docs"
  parts = "Shortcodes"
  weight = 250
categories = ["Shortcodes"]

recommended = false
featured = false
description = "Guide for Alpha's Call to Action shortcode. Add effective text-based Call To Action elements with a button to your homepage or section pages."
# SEO
seo_type = "TechArticle"
seo_image = "cta-shortcode-alpha-docs-seo.png"
+++
## Example:

{{< cta-example
TITLE="Latest Episode: The Last Donut"
BTN-TEXT="Listen Now"
BTN-LINK="#example"
BTN-LABEL="Listen to the full story now"
>}}

This week, we unravel the *baffling clues* and *chilling timeline* surrounding the disappearance of the **last donut**. 
What secrets remain buried? Learn more in our latest ***podcast***.

{{< /cta-example>}}

## Code
```go-html-template
{{</* cta
TITLE="Latest Episode: The Last Donut"
BTN-TEXT="Listen Now"
BTN-LINK="/podcast/the-last-donut"
BTN-LABEL="Listen to the full story now"
*/>}}

This week, we unravel the *baffling clues* and *chilling timeline* surrounding the disappearance of the **last donut**. 
What secrets remain buried? Learn more in our latest ***podcast***.

{{</* /cta */>}}
```
### Overview
A simple text-based **Call To Action** shortcode with **title**, Markdown styled **text content** and a **button styled link**. 

### Usage
- Use this shortcode on the **homepage** and/or **section pages** (i.e. `_index.md`).
- This shortcode **requires** both opening and closing tags.

### Parameters Reference

TITLE
: `TITLE="Example title"` --- (**string**, optional) 
: H2 heading.

BTN-TEXT
: `BTN-TEXT="Link text"` --- (**string**, optional) 
: Text for the button-styled link.

BTN-LINK
: `BTN-LINK="/link/to/path"` --- (**string**, optional) 
:  `href` attribute for button-styled link. Requires `BTN-TEXT` to be set.

BTN-LABEL
: `BTN-LABEL="Example label"` --- (**string**, optional) 
: `aria-label` attribute for button-styled link.

Inner Content 
: The main body of text. Supports Markdown formatting.

### Error Reporting
- Warnings are printed to the Hugo terminal.
- LiVa enabled.

#### Error Codes
liva-sc-141
: Unrecognized parameter detected.

liva-sc-142
: `BTN-LINK` is provided but `BTN-TEXT` is missing.
