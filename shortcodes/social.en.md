+++
# Content Identity
title = "Social Networks Shortcode"
description = "Documentation for Alpha's social shortcode. Display a list of social media icons-links from your configured menu."

# Authoring
author = "oxypteros"
date = "2025-05-31T16:23:43+02:00"
lastmod = "2025-07-14T10:51:47+02:00"
license = "CC-BY-SA"

# Organization
categories = ["Shortcodes"]

## Series
series = "Alpha Docs"
parts = "Shortcodes"
weight = 400

# Display
featured = false
recommended = false

# Publication Control
draft = false
layout = "page"
github_edit = true

# Advanced SEO
seo_type = "TechArticle"
seo_image = "social-shortcode-alpha-docs-seo.png"
+++
## Example:

{{< social-example LIMIT="17">}}

## Code
```go-html-template
{{</* social LIMIT="17" */>}}
```
### Overview
Renders a minimal list of social network links with icons for major platforms.

### Usage
- The shortcode will render the menu `sc_social` defined in your site's configuration file (`config/_default/menus.toml`).
- You can limit the number of entries shown using the optional `LIMIT` parameter. 
- For more details, refer to the [social menu documentation](/docs/config/menus-toml/#social-menus).
### Parameters Reference
LIMIT
: `LIMIT="5"` --- (**integer**, optional) 
: The number of items to display from the `sc_social` menu. 


#### Error Codes
liva-sc-220
: Unrecognized parameter detected.

liva-sc-221
: Invalid number or non integer value.

liva-sc-228
: Menu `sc_social` is not defined.


