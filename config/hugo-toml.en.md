+++
draft = false
date = "2025-05-30T15:58:13+02:00"
lastmod = ""
layout = "page"

title = "hugo.toml"
author = "oxypteros"
license = "CC-BY-SA"
github_edit = true
series = "Alpha Docs"
  parts = "Config Files"
  weight = 120
categories = ["Configuration"]

recommended = false
featured = false
description = "Configure Alpha theme: Understand hugo.toml setup, Alpha's defaults in config/_default/, best practices for root config, and key settings."
# SEO
seo_type = "TechArticle"
seo_image = "hugo-toml-alpha-docs-seo.png"
+++
{{< status-card TITLE="Before you begin" TYPE="warning">}}

If you **didn't** use the **Alpha Starter Site**, copy the entire **config folder** (`themes/alpha/config/`) to your site's root directory before editing anything. 
This ensures that your changes are preserved and won’t be overwritten by future Alpha updates.

{{< /status-card>}}

## Overview
Alpha’s `config/_default/hugo.toml` contains key configuration sections for:
- `[pagination]` --- controls pagination behavior.
- `[markup.goldmark]` --- defines markdown rendering options.
- `[markup.highlight]` --- sets syntax highlighting for code blocks.

These options are critical for Alpha’s layout, content rendering, and visual consistency.

## Usage
Alpha’s visual behavior depends on the values set inside the `hugo.toml` file located in the `config/_default/` directory. You should **not** modify or alter existing values unless you fully understand their function and can troubleshoot the outcome.

### Existing sites
If your project already uses its own `config/_default/` directory before adopting Alpha:
1. Create a **backup** of your existing config files.
```bash
mv config/_default config/_default.old
mv hugo.toml hugo.toml.old

```
2. Copy Alpha’s config folder to your root `config/`:
```bash
cp -r themes/alpha/config/_default config/

```
3. **Carefully merge any custom values** you had in your old config resolving all conflicts in favor of Alpha’s configuration
4. **Test** your site thoroughly before deploying.


If you're using a root level `hugo.toml`, be aware:
- Hugo prioritizes the root level config file over the one in `config/_default/`.
- If the same key exists in both `hugo.toml` and `config/_default/hugo.toml` the value from the root file will take precedence. This may lead to misconfigurations if you're not aware of the override.

#### Required Keys in Root hugo.toml
To avoid conflicts, the following keys are not included in Alpha’s `config/_default/hugo.toml` and must be added manually to the root `hugo.toml` if not already present:
```toml
baseURL = "https://example.com"
title = "My Website"
timeZone = "Europe/Rome"
theme = "alpha"
```
## Best Practices
Alpha recommends using **both** a root level `hugo.toml` and a `config/_default/hugo.toml`:
- This dual structure provides a soft separation between Alpha theme keys and site specific keys.
- Facilitates switching to a different theme in the future without losing essential project settings.
```bash
my-project/
├── hugo.toml  (Site-specific: baseURL, title, theme, languageCode, timeZone)
├── config/
    └── _default/
        └── hugo.toml (Alpha's defaults: pagination, markup, etc.)
```
## Keys Reference [^1]
theme
: `theme = "alpha"` --- (**string, required**)
: Instructs Hugo to use the Alpha theme. 
: Recommended placement: root `hugo.toml`.

baseURL  
: `baseURL = "https://example.com"` --- (**string, required**)
: The URL of your deployed site. 
: Recommended placement: root `hugo.toml`.

title 
: `title = "My Website"` --- (**string, recommended**)
: Defines the website name. Used on every page, for the pseudologo (if enabled) and in metadata fields.
: Recommended placement: root `hugo.toml`.
: If missing, triggers the `ocd-config-100` error.

timeZone
: `timeZone = "Europe/Rome"` --- (**string**, optional)
: The timezone used for the content date. Define the timezone for the `date` and `lastmod` keys in the frontmatter.
: Use a valid TZ identifier from [this list](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones/ "Wikipedia page listing the tz database time zones").
: Recommended placement: root `hugo.toml`.

pagerSize 
: `pagerSize = 10` --- (**integer**, optional)
: Defines the number of items per page before pagination. 
: Located under `[pagination]` section. Default value: `10`
: Predefined in `config/_default/hugo.toml`.

[^1]: These are the only keys you need to change in the `hugo.toml` to customize your Alpha Hugo site.