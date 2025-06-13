+++
draft = false
date = "2025-05-31T10:48:52+02:00"
lastmod = ""
layout = "page"

title = "Featured Article Shortcode"
author = "oxypteros"
license = "CC-BY-SA"
github_edit = true
series = "Alpha Docs"
  parts = "Shortcodes"
  weight = 200
categories = ["Shortcodes"]

recommended = false
featured = false
description = "Learn how to use the featured shortcode in the Alpha Hugo theme to display highlighted posts on your homepage or section pages. Supports multiple styles like plain, simple, and banner."
# SEO
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
- Set `featured = true` in the frontmatter of the content page you want to feature.
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
: Accepted values:`banner`, `simple`, `plain`
: If omitted, the default style is `plain`
