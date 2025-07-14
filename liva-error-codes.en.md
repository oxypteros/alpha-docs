+++
# Content Identity
title = "Liva Error Codes"
description = ""

# Authoring
author = "oxypteros"
date = "2025-07-12T12:35:08+02:00"
lastmod = ""
license = ""

# Organization
categories = ["Content"]

## Series
series = "Alpha Docs"
parts = "LiVa Codes"
weight = 999

# Display
featured = false
recommended = false


# Publication Control
draft = true
layout = "page"
github_edit = true

# Advanced SEO
seo_type = "TechArticle"
+++

## LiVa Error Code Reference
Below is a reference of the codes that LiVa reports when an error is detected.

### Config Files
#### liva-cfg-102
`title` value is missing in `hugo.toml`.

#### liva-cfg-112
`weight` value is missing for a language in `config/_default/languages.toml`.

#### liva-cfg-113
`languageName` value is missing for a language in `config/_default/languages.toml`.

#### liva-cfg-121
`established_year` value is not a valid year in `config/_default/params.toml`.

#### liva-cfg-122
`established_year` has a future year value in `config/_default/params.toml`.

#### liva-cfg-132
`seo_default_image` declared in `config/_default/params.toml` cannot be found.

#### liva-cfg-133
`seo_default_image` declared in `config/_default/params.toml` does not meet the recommended resolution.

### Frontmatter
#### liva-fm-102
`lastmod` value precedes the published date.

#### liva-fm-111
`layout` value is invalid.