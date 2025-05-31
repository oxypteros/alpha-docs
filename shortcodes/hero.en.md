+++
draft = false
date = "2025-05-31T10:25:57+02:00"
lastmod = ""
layout = "page"

title = "Hero"
author = "oxypteros"
license = "CC0"
series = "Alpha Docs"
  parts = "Shortcodes"
  weight = 190
categories = ["Shortcodes"]

recommended = false
featured = false
description = "Documentation for Alpha's hero shortcode. Create a text-based hero section with title, subtitle, and two call-to-action links. Ideal for homepages or section intros."
+++
## Example:
{{< hero-example
TITLE="An awesome title!"
SUBTITLE="A subtitle that complements the title." 
BTN-TEXT="Start reading"
BTN-LINK="#example"
BTN-LABEL="Read my first post now"
LINK-TEXT="View all posts"
LINK="#example"
LINK-LABEL="View a complete list of my posts"
>}}

## Code
```go-html-template
{{</* hero
TITLE="An awesome title!"
SUBTITLE="A subtitle that complements the title." 
BTN-TEXT="Start reading"
BTN-LINK="/posts/my-first-post"
BTN-LABEL="Read my first post now"
LINK-TEXT="View all posts"
LINK="/posts"
LINK-LABEL="View a complete list of my posts"
*/>}}
```
### Overview
A simple text-based hero shortcode with **title**, **subtitle**, and **two links**. (One styled as a *button* and one as a *standard link*.) 

### Usage
Use on *homepage* and/or *section pages* (`_index.md`).

**Tip:** Paste this shortcode at the top of your `_index.md` file to add a hero section.
### Parameters Reference
TITLE
: `TITLE = "Example Title"` ---  (**string**, optional) 
: H2 heading. Falls back to the **page title** if not provided. 

SUBTITLE 
: `SUBTITLE = "Example Subtitle"` --- (**string**, optional) 
: H3 heading.

BTN-TEXT
: `BTN-TEXT = "Link 1 text"` --- (**string**, optional) 
: Text for the button-styled link.

BTN-LINK 
: `BTN-LINK = "/link/to/path"` --- (**string**, optional) 
:  `href` attribute for button-styled link. Requires `BTN-TEXT` to be set.

BTN-LABEL 
: `BTN-LABEL = "Example label"` --- (**string**, optional) 
: `aria-label` attribute for button-styled link.

LINK-TEXT 
: `LINK-TEXT = "Link 2 text"` --- (**string**, optional) 
: Text for the secondary link.

LINK 
: `LINK = "/link/to/path"` --- (**string**, optional) 
: `href` attribute for the secondary link. Requires `LINK-TITLE` to be set. 

LINK-LABEL 
: `LINK-LABEL = "Example label"` --- (**string**, optional) 
: `aria-label` attribute for the secondary link. (string, optional)

### Error Reporting
- Warnings are printed to the Hugo terminal.
- OCD enabled.

#### Error Codes
ocd-sc-121
: Unrecognized parameter detected.

ocd-sc-122
: `BTN-LINK` is provided but `BTN-TEXT` is missing.

ocd-sc-123
: `LINK` is provided but `LINK-TEXT` is missing.