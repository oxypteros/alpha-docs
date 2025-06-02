+++
draft = false
date = "2025-05-30T16:47:35+02:00"
lastmod = ""
layout = "page"

title = "params.toml"
author = "oxypteros"
license = "CC0"
github_edit = true
series = "Alpha Docs"
  parts = "Config Files"
  weight = 150
categories = ["Configuration"]

recommended = false
featured = false
description = "Alpha's params.toml guide: Control theme specific settings for layout (pseudologo, motto), features (prefetch, search), integrations, and admin options."
+++
{{< status-card TITLE="Before we begin" TYPE="warning">}}
If you **didn't** use the **Alpha Starter Site**, copy the entire **config folder** (`themes/alpha/config/`) to your site's root directory before editing anything. 
This ensures that your changes are preserved and won’t be overwritten by future Alpha updates.
{{< /status-card>}}

## Overview
The `config/_default/params.toml` file contains all **customs** and **Alpha specific** configuration keys.

## Usage
In the order they appear in `params.toml`:
```toml
# Header Settings
pseudologo_enabled = true

# Footer Settings
established_year = "2025"
motto = "\"Unleash your words\""

# Performance Settings
prefetch_enabled = true

# Integrations
pagefind_enabled = false
goatcounter_prefix = ""

# Visitor Settings
noCookies_snackbar = true
visitor_settings = true

#Development Settings
tailwind_enabled = false
ocd_enabled = true
```

## Best Practices
You’re free to enable, disable, or customize each key to suit your site’s needs. Keys that require further explanation (such as `ocd_enabled` or `tailwind_enabled`) have dedicated pages in the [Alpha documentation](/docs).

## Keys Reference
pseudologo_enabled
: `pseudologo_enabled = true`--- (**boolean**, optional)
: Enables a pseudo logo. The first letter of your site name, stylized as a minimalist logo.
: Default value: `true`

established_year
: `established_year = "2025"` --- (**string**, optional)
: Defines your site's founding year. Used to calculate the copyright
notice in the footer (`© 2025–CurrentYear`).
: If omitted fallback to the current year as default value.

motto
: `motto = "\"Unleash your words\""` --- (**string**, optional)
: A short tagline motto shown in the footer. 

noCookies_snackbar
: `noCookies_snackbar =  true` --- (**boolean**, optional)
: Displays a snackbar with a policy message with a hardcoded `/policy` link.
: Default value: `true`

visitor_settings
: `visitor_settings = true`--- (**boolean**, optional)
: Adds a settings icon in the footer that opens a modal.
: Allows users to opt out of anonymous tracking and disable link prefetching to save data.
: Default value: `true`

ocd_enabled
: `ocd_enabled = true` --- (**boolean**, optional)
: Enables the OCD for local development.
: Default value: `true`

prefetch_enabled
: `prefetch_enabled = true` --- (**boolean**, optional)
: Activates prefetching for key links to enable near instant page transitions.
: Default value: `true`

tailwind_enabled
: `tailwind_enabled = false` --- (**boolean**, optional)
: Enables Tailwind CSS integration if Tailwind is installed and configured in Hugo.
: Default value: `false`

pagefind_enabled
: `pagefind_enabled = false` --- (**boolean**, optional)
: Enables Alpha’s built-in search functionality using Pagefind.
: Default value: false

goatcounter_prefix
: `goatcounter_prefix = "alpha"` --- (**string**, optional)
: Defines your GoatCounter site ID. Enables anonymous traffic analytics if set.
