+++
# Content Identity
title = "LiVa"
description = "An overview of the LiVa helper and how it aids with Alpha theme configuration and troubleshooting."

# Authoring
author = "oxypteros"
date = "2025-05-30T17:39:54+02:00"
lastmod = "2025-07-12T13:21:07+02:00"
license = "CC-BY-SA"

# Organization
categories = ["Content"]

## Series
series = "Alpha Docs"
parts = "LiVa"
weight = 160

# Display
featured = false
recommended = false

# Publication Control
draft = false
layout = "page"
github_edit = true

# Advanced SEO
seo_type = "TechArticle"
seo_image = "liva-alpha-docs-seo.png"
+++
{{< text_snippet TITLE="Your Content Assistant">}}

LiVa (*Linting Validator*) is a simple helper for everything Alpha-related. It assists with **almost every theme issue** you might encounter and helps with your daily use of the theme.

{{< /text_snippet >}}

## Overview

LiVa started as a personal development logger during early Alpha configuration. It proved useful while setting up templates and shortcodes, so over time, it evolved into an actual tool.

LiVa helps detect **misconfigurations** in both config and content files. Its purpose is to assist your workflow. While it is part of Alpha, you should think of it more as a **symbiotic independent entity** rather than just a feature.

LiVa will detect and report crucial issues in config files, frontmatter, Markdown, and shortcodes that can affect your deployed site if left unresolved.

Detected issues appear as warnings or errors on the page and in the Hugo terminal.

## Usage

LiVa is **enabled by default** in Alpha. You can disable it in your `config/_default/params.toml` file:

```toml
liva_enabled = false
livaWarn_enabled = false
```

> LiVa runs **only in your local development environment**. 
> It does **not** affect production builds in any way.

When enabled, you'll see a *floating action button* (**FAB**) at the bottom-right corner of the screen.
- If no errors are detected, clicking the FAB will open the **settings menu**, where you can:
  - Change the **FAB position** (left/right)
  - Open the **LiVa Console**
  - Check for Alpha and Hugo **updates**
- If an **error** is detected, the FAB turns **red** and clicking it opens the LiVa Console, which:
  - Describes the issue(s).
  - Suggests how to fix them.
- All LiVa errors appear as warnings in the Hugo server terminal.
- Shortcode and frontmatter related errors are also displayed directly on the affected page during local development.

You can think of LiVa as a **second line of defense**, supplementing Hugo’s built-in warning and error system.
However, **LiVa will never break your build**, so it’s your responsibility to resolve any errors it reports before deploying your site.

### Interacting with LiVa
LiVa requires **no additional configuration**. Under normal conditions, it runs quietly in the background, detecting, reporting, and clearing errors as you work. It’s designed **not to interfere** with your workflow.

If you encounter any issues with LiVa or Alpha, you can:
- Click the “Report an Alpha issue” icon in the LiVa Console.
- Or contact me directly.

If you experience a **persistent error** that doesn’t go away (even after resolving the cause), use the *“LiVa reset errors”* button inside the console or restart `hugo server`.

### Limitations
The LiVa on-page reporting has one main limitation.

> Most errors are **not** detected until you **visit** the page containing them.

Resolving this limitation would require adding dependencies, which I want to avoid to keep LiVa fully **self-contained** and **out-of-the-box** for all Alpha users.

To work around this, simply check the Hugo terminal. Terminal warnings are scoped globally and will also appear during the final `hugo` build.
Or  make sure to **manually preview the pages you edit or create** in your local environment.

{{< status_card TITLE="Attention" TYPE="warning">}}

LiVa can inform, but it **cannot fix errors** automatically.
If no error is shown on page, that doesn't necessarily mean everything is working perfectly. 
**Always** check your terminal and resolve possible LiVa issues before release.

{{< /status_card >}}



