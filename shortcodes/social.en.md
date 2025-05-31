+++
draft = false
date = "2025-05-31T16:23:43+02:00"
lastmod = ""
layout = "page"

title = "Social Networks"
author = "oxypteros"
license = "CC0"
series = "Alpha Docs"
  parts = "Shortcodes"
  weight = 400
categories = ["Shortcodes"]

recommended = false
featured = false
description = "Documentation for Alpha's social shortcode. Display a list of social media icons-links from your configured menu."
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
- The shortcode will render the menu `sc_social` defined in your site's configuration file (`/config/_default/menus.toml`).
- You can limit the number of entries shown using the optional `LIMIT` parameter. 
- For more details, refer to the [social menu documentation](/docs/config/menus-toml/#social-menus).

### Parameters Reference
LIMIT
: `LIMIT="5"` --- (**integer**, optional) 
: The number of items to display from the `sc_social` menu. 

### Error Reporting
- Warnings are printed to the Hugo terminal.
- OCD enabled.

#### Error Codes
ocd-sc-171
: Unrecognized parameter detected.

ocd-sc-172
: Menu `sc_social` is not defined.

ocd-sc-173
: Invalid value for parameter `LIMIT`. Must be an integer.
