+++
draft = false
date = "2025-06-03T15:57:40+02:00"
lastmod = ""
layout = "page"

title = "Single Language"
author = "oxypteros"
license = "CC0"
github_edit = true
series = "Alpha Docs"
  parts = "Multilingual"
  weight = 500
categories = ["Content"]

recommended = false
featured = false
description = "Use Alpha Hugo theme in a single language other than English. Learn to set your default language (e.g., French, Spanish) in languages.toml."
+++
If you're planning to use Alpha exclusively in a language **other than English**, you need to tell Hugo that your **default language** is **not** English.

## Set Up Another Language

To do that, edit the `/config/_default/languages.toml` configuration file.
By default, this file contains:
```toml
[en]
  weight = 1
  languageName = "English"
  languageCode = "en"
```
For example, if you want to use **Canadian French**, you should **edit** (not add a new block) the existing section to this:

```toml
[fr]
  weight = 1
  languageName = "Français"
  languageCode = "fr-CA"
```
**Note**: See the [language.toml documentation](/docs/config/languages-toml/) for more details.

## Creating Content in the New Language
Since your site remains single-language, you can [create your content](/docs/content-creation/) using Alpha’s recommended approach, just make sure your actual content is written in the selected language.

Hugo will automatically tag each page with the appropriate language code so that search engines know how to interpret your content.

If there's **even a small chance** you'll add more languages later, it's worth reading the next part. Otherwise, feel free to skip ahead to [Translating Alpha](/docs/multilingual/translating-alpha)