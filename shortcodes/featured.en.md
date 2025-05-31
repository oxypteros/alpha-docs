+++
draft = false
date = "2025-05-31T10:48:52+02:00"
lastmod = ""
layout = "page"

title = "Featured"
author = "oxypteros"
license = "CC0"
series = "Alpha Docs"
  parts = "Shortcodes"
  weight = 200
categories = ["Shortcodes"]

recommended = false
featured = false
description = "Learn how to use the featured shortcode in the Alpha Hugo theme to display highlighted posts on your homepage or section pages. Supports multiple styles like plain, simple, and banner."
+++
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
- Use this shortcode on the homepage and/or section pages (i.e. _index.md).

**Tip:** Only one featured post is shown at a time. If multiple posts are marked, the most recent one (*by date*) is selected.
### Parameters Reference
TYPE
: `TYPE="plain"` ---  (**string**, optional) 
: Controls the visual style of the featured section.
: Accepted values:`banner`, `simple`, `plain`
: If omitted, the default style is `plain`

Lowest priority. Tasks that can be deferred.