+++
# Content Identity
title = "params.toml"
description = "Alpha theme params.toml guide: Control theme specific settings for layout, features, integrations, and developer options."

# Authoring
author = "oxypteros"
date = "2025-05-30T16:47:35+02:00"
lastmod = "2025-07-11T19:02:11+02:00"
license = "CC-BY-SA"

# Organization
categories = ["Configuration"]

## Series
series = "Alpha Docs"
parts = "Config Files"
weight = 150

# Display
featured = false
recommended = false

# Publication Control
draft = false
layout = "page"
github_edit = true

# Advanced SEO
seo_type = "TechArticle"
seo_image = "params-toml-alpha-docs-seo.png"
+++
{{< status_card TITLE="Before you begin" TYPE="warning">}}

If you **didn't** use the **Alpha Starter Site**, copy the entire **config folder** (`themes/alpha/config/`) to your site's root directory before editing anything. 
This ensures that your changes are preserved and won’t be overwritten by future Alpha updates.

{{< /status_card>}}

## Overview
The `config/_default/params.toml` file contains all **customs** and **Alpha specific** configuration keys.

## Usage
In the order they appear in `params.toml`:
```toml
# Site Appearance
pseudologo_enabled = true
established_year = "2025"
motto = "Site motto or tagline"

# Privacy
visitor_settings = true
noCookies_snackbar = true

# Integrations
pagefind_enabled   = true
goatcounter_prefix = "[site_ID]"

# Performance
prefetch_enabled = true

# Global SEO Settings
seo_default_image = "sharing-image.png" 
seo_logo_url = "https://example.com/logo.svg" 
seo_license_url = "https://creativecommons.org/licenses/by/4.0/"
seo_organization = "[organization_name]"
seo_author = "[author_name]"
seo_author_url = "https://absolute/url/author_profile" 
seo_twitter_username = "@TwitterUsername"

# "Add to Home Screen" Settings
seo_manifest_short_name  = "My Blog"
seo_manifest_theme_color = "#ffffff" 
seo_manifest_bg_color    = "#ffffff"

# Development Settings
tailwind_enabled = false 

# LiVa Settings 
liva_enabled = true     
livaWarn_enabled = true 
```

## Best Practices
You’re free to enable, disable, or customize each key to suit your site’s needs. Keys that require further explanation have dedicated pages in the documentation.

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
: Invalid values triggers the `liva-cfg-121`, `liva-cfg-122` warning.

motto
: `motto = "\"Unleash your words\""` --- (**string**, optional)
: A short tagline motto shown in the footer.

visitor_settings
: `visitor_settings = true`--- (**boolean**, optional)
: Adds a settings icon in the footer that opens a modal.
: Allows users to opt-out of anonymous tracking and disable link prefetching to save data.
: Default value: `true`

noCookies_snackbar
: `noCookies_snackbar =  true` --- (**boolean**, optional)
: Displays a snackbar with a policy message.
: Default value: `true`

pagefind_enabled
: `pagefind_enabled = false` --- (**boolean**, optional)
: Enables Alpha’s built-in search functionality using Pagefind.
: Default value: `false` ([Pagefind integration](/docs/integrations/search/))

goatcounter_prefix
: `goatcounter_prefix = "alpha"` --- (**string**, optional)
: Defines your GoatCounter site ID. Enables anonymous traffic analytics if set.
: [GoatCounter integration](/docs/integrations/analytics/)

prefetch_enabled
: `prefetch_enabled = true` --- (**boolean**, optional)
: Activates prefetching for key links to enable near instant page transitions.
: Default value: `true`

seo_default_image
: `seo_default_image = "sharing-image.png"` --- (**string**, optional) 
: Image for content sharing on social networks.
: Place the image in `assets/img` and reference the filename as value.
: Overridden by the `seo_image` key in frontmatter. 
: Triggers the `liva-cfg-132`, `liva-cfg-132` error and warning for missing and bad quality image

seo_logo_url
: `seo_logo_url = "https://example.com/img/logo.svg"` --- (**string**, optional)
: The URL of the website's logo, used for `schema.org` structured data.

seo_license_url
: `seo_license = "https://creativecommons.org/licenses/by/4.0/"` --- (**string**, optional)
: A license URL, used for `schema.org` structured data. 
: Overridden by the `license` key in frontmatter.

seo_organization
: `seo_organization = "My Website"` --- (**string**, optional)
: The organization name, used for `schema.org` structured data. 
: Default: The `title` from your `hugo.toml` is used.

seo_author
: `seo_author = "John Smith"` --- (**string**, optional)
: The author name, used for `schema.org` structured data. 
: Overridden by the `author` key in frontmatter.

seo_author_url
: `seo_author_url = "https://www.linkedin.com/in/user_profile"` --- (**string**, optional)
: The URL of the author's primary social media profile or personal website. Is used for Open Graph.

seo_twitter_username
: `seo_twitter_username = "@TwitterUsername"` --- (**string**, optional)
: The primary Twitter handle associated with the entire website. Used in Twitter Cards.

seo_manifest_short_name
: `seo_manifest_short_name = "My Blog"` --- (**string**, optional)
: The name displayed beneath the site's icon when added to a mobile device's home screen. This should be kept brief.
: Default: The `title` from your `hugo.toml`.

seo_manifest_theme_color
: `seo_manifest_theme_color = "#ffffff"` --- (**string**, optional)
: Sets the color of the browser UI or status bar when the site is launched from the home screen.
: Default value: `#ffffff`

seo_manifest_bg_color
: `seo_manifest_bg_color = "#ffffff"` --- (**string**, optional)
: Defines the background color of the splash screen that is displayed while the site is loading after being launched from the home screen.
: Default value: `#ffffff`

tailwind_enabled
: `tailwind_enabled = false` --- (**boolean**, optional)
: Enables Tailwind CSS integration if Tailwind is installed and configured in Hugo.
: Default value: `false`

liva_enabled
: `liva_enabled = true` --- (**boolean**, optional)
: Enables the LiVa validation for local development.
: Default value: `true` ([LiVa documentation](/docs/liva/))

livaWarn_enabled
: `livaWarn_enabled = true` --- (**boolean**, optional)
: Enables the LiVa terminal validation for local development. 
: Default value: `true` ([LiVa documentation](/docs/liva/))