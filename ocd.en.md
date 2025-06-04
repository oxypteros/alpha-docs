+++
draft = false
date = "2025-05-30T17:39:54+02:00"
lastmod = ""
layout = "page"

title = "OCD"
author = "oxypteros"
license = "CC0"
github_edit = true
series = "Alpha Docs"
  parts = "OCD"
  weight = 160
categories = ["Content"]

recommended = false
featured = true
description = "An overview of the OCD helper and how it aids with Alpha theme configuration and troubleshooting."
+++
{{< text-snippet TITLE="Your Alpha Content Assistant">}}
OCD is a rudimentary helper for everything Alpha related. It can assist with **almost every theme issue** you might encounter and help with your daily use of the theme.
{{< /text-snippet >}}

## Overview
OCD began as a personal development logger during the early configuration of Alpha's templates and shortcodes. It proved helpful during early Alpha configuration and content creation, so over time, it evolved into an actual tool.

OCD helps detect **misconfigurations** in both config and content files. Its goal is to assist your workflow. While currently functional, it is still in **beta** and will continue improving with every Alpha release.

## Usage

OCD is **enabled by default** in Alpha. You can disable it in your `config/_default/params.toml` file:

```toml
ocd_enabled = false
```
**Note:** OCD runs **only in your local development environment**. It does **not** affect production builds in any way.

When enabled, you'll see a *floating action button* (**FAB**) at the bottom-right corner of the screen.
- If no errors are detected, clicking the FAB will open the **settings menu**, where you can:
  - Change the **FAB position** (left/right)
  - Open the **OCD Console**
  - Check for Alpha and Hugo **updates**
- If an **error** is detected, the FAB turns **red** and clicking it opens the OCD Console, which:
  - Describes the issue(s).
  - Suggests how to fix them.
- Shortcode and frontmatter related errors are also displayed directly on the page during local development.
- Additionally, all OCD errors appear as warnings in the Hugo server terminal.

You can think of OCD as a **second line of defense**, supplementing Hugo’s built-in warning and error system.
However, **OCD will never break your build**, so it’s your responsibility to resolve any errors it reports before deploying your site.

### Interacting with OCD
OCD requires **no additional configuration**. Under normal conditions, it runs quietly in the background, detecting, reporting, and clearing errors as you work. It’s designed **not to interfere** with your workflow.

Although thoroughly tested before its initial Alpha release, OCD remains in beta. If you encounter any issues with OCD or Alpha, you can:
- Click the *“Report an Alpha issue”* icon in the OCD Console. 
- Or contact me directly

If you experience a **persistent error** that doesn’t go away (even after the issue is resolved), or you simply want to clear all current messages, use the *“OCD reset errors”* button inside the console.

### Limitations
OCD has one significant limitation.

> Most errors are **not** detected until you **visit** the page containing them.

Resolving this limitation would require adding dependencies, which I want to avoid to keep OCD fully **self-contained** and **out-of-the-box** for all Alpha users.

To overcome this, you should **manually preview the pages you edit or create** in your local environment to ensure no errors go undetected.

{{< status-card TITLE="Attention" TYPE="warning">}}
OCD can inform, but it **cannot fix errors** automatically.
If no error is shown, that doesn't necessarily mean everything is working perfectly, always validate your site thoroughly before release.
{{< /status-card >}}

## Error Code Reference [^1]
ocd-config-100
: `title` value is missing in `hugo.toml`

ocd-lang-100
: `languageName` value is missing in `config/_default/languages.toml`

ocd-params-100
:  Invalid `established_year` value set in `config/_default/params.toml`

ocd-params-101
: `established_year` value set to future year in `config/_default/params.toml`

[^1]: Incomplete list (under development)