+++
# Content Identity
title = "Translating Alpha"
description = "Learn how to translate Alpha Hugo theme's interface. Step-by-step guide to creating i18n files for a fully localized site"

# Authoring
author = "oxypteros"
date = "2025-06-03T16:20:52+02:00"
lastmod = "2025-07-14T15:00:20+02:00"
license = "CC-BY-SA"

# Organization
categories = ["Content"]

## Series
series = "Alpha Docs"
parts = "Multilingual"
weight = 520

# Display
featured = false
recommended = false

# Publication Control
draft = false
layout = "page"
github_edit = true

# Advanced SEO
seo_type = "TechArticle"
seo_image = "translating-alpha-docs-seo.png"
+++
Even if your content is in one or more languages other than English, Alpha's **interface** remains in English by default. To build a complete and consistent multilingual website, you’ll need to **translate Alpha** itself into your language(s).

## How to Translate Alpha
1. Copy the file `/themes/alpha/i18n/en.toml` into your site’s `i18n/` root folder.
2. Rename the copied file to match the language code you defined in `config/_default/languages.toml`.

For example, if your `languages.toml` defines Spanish and Italian like this:
```toml
[es]
  languageName = "Español"
  languageCode = "es"  
  weight = 1

[it]
  languageName = "Italiano"
  languageCode = "it" 
  weight = 2
```
Then, in your site's `i18n/` folder, you would create (by copying and renaming `en.toml`):
- `es.toml` (for Spanish)
- `it.toml` (for Italian)

### What to Translate
Each translation file contains entries in the following format:
```toml
[Identifier]
one = "Single value"
other = "Plural value"
```
Do **not** change the `[Identifier]`. You only need to translate the `one` and `other` values.

Example: the first entry in `en.toml` is:
```toml
[Homepage]
other = "Homepage"
```
In Spanish (`es.toml`) would be :
```toml
[Homepage]
other = "Página Principal"
```
and in Italian (`it.toml`):

```toml
[Homepage]
other = "Pagina Iniziale"
```
Repeat this process for each entry in the file.

## 404 Page Translation
Alpha provides a custom **404 error page**. If your site is multilingual or in a different language, then copy the default English `404.en.html` (`themes/alpha/layouts/404.en.html`) into your site's root `layouts/` folder and rename it using the language code.

For example for Spanish:
```
layouts/404.es.html
```
and for Italian:
```
layouts/404.it.html
```

{{< faq TITLE="Questions no one asked" SUBTITLE="But I’m answering them anyway.">}}

## Can I Share My Translation?
Yes! If you’ve translated Alpha and would like to share it with other users, please follow the instructions on the [Support](/support/) page.
## What about RTL Language Support
Unfortunately, Alpha **does not** currently support right-to-left (RTL) languages. This may change in the future.

{{< /faq >}}
