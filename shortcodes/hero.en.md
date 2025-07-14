+++
# Content Identity
title = "Hero Shortcode"
description = "Documentation for Alpha's hero shortcode. Create a text-based hero section with title, subtitle, and two call-to-action links. Ideal for homepages or section intros."

# Authoring
author = "oxypteros"
date = "2025-05-31T10:25:57+02:00"
lastmod = "2025-07-14T09:19:19+02:00"
license = "CC-BY-SA"

# Organization
categories = ["Shortcodes"]

## Series
series = "Alpha Docs"
parts = "Shortcodes"
weight = 190

# Display
featured = false
recommended = false

# Publication Control
draft = false
layout = "page"
github_edit = true

# Advanced SEO
seo_type = "TechArticle"
seo_image = "hero-shortcode-alpha-docs-seo.png"
+++
## Example:

{{< hero-example
TITLE="Beyond the Yellow Tape!"
SUBTITLE="We investigate the stories others overlook." 
BTN-TEXT="Start reading"
BTN-LINK="#example"
BTN-LABEL="Read our research for the case of The Last Donut"
LINK-TEXT="View all cases"
LINK="#example"
LINK-LABEL="View a complete list of our cases"
>}}

## Code
```go-html-template
{{</* hero
TITLE="Beyond the Yellow Tape!"
SUBTITLE="We investigate the stories others overlook." 
BTN-TEXT="Start reading"
BTN-LINK="/cases/the-last-donut"
BTN-LABEL="Read our research for the case of The Last Donut"
LINK-TEXT="View all cases"
LINK="/posts"
LINK-LABEL="View a complete list of our cases"
*/>}}
```
### Overview
A simple text-based hero shortcode with **title**, **subtitle**, and **two links**. (One styled as a *button* and one as a *standard link*.) 

### Usage
- Use on *homepage* and/or *section pages* (`_index.md`).
- The `TITLE` and `SUBTITLE` values use their **last character** as a decorative element (*different color*). For best aesthetics, it’s **strongly recommended** to end both with a **punctuation mark** (e.g. `.` `?` `!` `:` `;`).

**Tip:** Paste this shortcode at the top of your `_index.md` file to add a hero section.
### Parameters Reference
TITLE
: `TITLE="Example Title"` ---  (**string**, optional) 
: H2 heading. Falls back to the **page title** if not provided. 

SUBTITLE 
: `SUBTITLE="Example Subtitle"` --- (**string**, optional) 
: H3 heading.

BTN-TEXT
: `BTN-TEXT="Link 1 text"` --- (**string**, optional) 
: Text for the button-styled link.

BTN-LINK 
: `BTN-LINK="/link/to/path"` --- (**string**, optional) 
:  `href` attribute for button-styled link. Requires `BTN-TEXT` to be set.

BTN-LABEL 
: `BTN-LABEL="Example label"` --- (**string**, optional) 
: `aria-label` attribute for button-styled link.

LINK-TEXT 
: `LINK-TEXT="Link 2 text"` --- (**string**, optional) 
: Text for the secondary link.

LINK 
: `LINK="/link/to/path"` --- (**string**, optional) 
: `href` attribute for the secondary link. Requires `LINK-TITLE` to be set. 

LINK-LABEL 
: `LINK-LABEL="Example label"` --- (**string**, optional) 
: `aria-label` attribute for the secondary link. (string, optional)

#### Error Codes
liva-sc-110
: Unrecognized parameter detected.

liva-sc-112
: Incomplete link/text pair.