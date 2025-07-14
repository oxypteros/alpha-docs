+++
# Content Identity
title = "Help Shortcode"
description = "Display local-only help cheatsheets for Markdown and shortcodes using LiVa UI."

# Authoring
author = "oxypteros"
date = "2025-07-14T08:58:24+02:00"
license = "CC-BY-SA"

# Organization
categories = ["Shortcodes"]
## Series
series = "Alpha Docs"
parts = "Shortcodes"
weight = 185

# Display
featured = false
recommended = false


# Publication Control
draft = false
layout = "page"
github_edit = false

# Advanced SEO
seo_type = "TechArticle"
seo_image = "help-shortcode-alpha-docs-seo.png"
+++
{{< status_card TITLE="Note" TYPE="warning" >}}

This shortcode is part of **Alpha’s LiVa system** and will not work unless **LiVa is enabled**. Its goal is to improve the writing workflow, **not** for end-user display.

{{< /status_card >}}

## Code
```go-html-template
{{</* help TYPE="markdown" */>}}
```
### Overview
The **help** shortcode displays a quick-reference cheatsheet directly inside the page using the LiVa UI.
It is meant as an authoring-time helper, it renders only during local development and **does not appear** in production builds.

Use it as an in-browser guide to check available shortcode syntax or Markdown formatting rules without leaving your project.

To function, LiVa must be active:
- `liva_enabled = true` in `config/_default/params.toml`
- Site running in development mode (`hugo server`)

### Usage
- Place the shortcode anywhere in your content where you want help displayed.
- Preview the page in your browser to see the cheatsheet appear.


### Parameters Reference

TYPE
: `TYPE="markdown"` --- (**string**, optional) 
: Defines which cheatsheet to show.
: TYPE values: `markdown`, `shortcodes` (default)

#### Error Codes

liva-sc-100
: Unrecognized parameter detected.

liva-sc-101
: Invalid value detected