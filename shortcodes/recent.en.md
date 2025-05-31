+++
draft = false
date = "2025-05-31T14:50:40+02:00"
lastmod = ""
layout = "page"

title = "Recent Posts"
author = "oxypteros"
license = "CC0"
github_edit = true
series = "Alpha Docs"
  parts = "Shortcodes"
  weight = 240
categories = ["Shortcodes"]

recommended = false
featured = false
description = "Display a list of recent posts with optional title and limit. Automatically highlights new content."
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
