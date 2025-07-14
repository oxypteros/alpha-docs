+++
# Content Identity
title = "Single Language"
description = "Use Alpha Hugo theme in a single language other than English. Learn to set your default language (e.g., French, Spanish) in languages.toml."

# Authoring
author = "oxypteros"
date = "2025-06-03T15:57:40+02:00"
license = "CC-BY-SA"

# Organization
categories = ["Content"]

## Series
series = "Alpha Docs"
parts = "Multilingual"
weight = 500

# Display
featured = false
recommended = false

# Publication Control
draft = false
layout = "page"
github_edit = true

# Advanced SEO
seo_type = "TechArticle"
seo_image = "single-language-alpha-docs-seo.png"
+++
If you're planning to use Alpha exclusively in a language **other than English**, you need to tell Hugo that your **default language** is **not** English.

## Set Up Another Language

To do that, edit the `config/_default/languages.toml` configuration file.
By default, this file contains:
```toml
[en]
  languageName = "English"
  languageCode = "en"
  weight = 1
```
If you want, for example, to use **Canadian French**, you should **edit** (not add a new block) the existing section to this:

```toml
[fr]
  languageName = "Français"
  languageCode = "fr-CA" 
  weight = 1
```
**Note**: See the [language.toml documentation](/docs/config/languages-toml/) for more details.

## Creating Content in the New Language
Since your site remains single-language, you can [create your content](/docs/content-creation/) using Alpha’s recommended approach, just make sure your actual content is written in the selected language.

Hugo will automatically tag each page with the appropriate language code so that search engines know how to interpret your content.

If there's **even a small chance** you'll add more languages later, it's worth reading the next part. Otherwise, feel free to skip ahead to [Translating Alpha](/docs/multilingual/translating-alpha/)