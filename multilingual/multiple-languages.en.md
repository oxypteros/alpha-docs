+++
# Content Identity
title = "Multiple Languages"
description = "Set up a multilingual Alpha Hugo site. Configure languages, create translated content, and manage URL slugs."

# Authoring
author = "oxypteros"
date = "2025-06-03T16:05:12+02:00"
license = "CC-BY-SA"

# Organization
categories = ["Content"]

## Series
series = "Alpha Docs"
parts = "Multilingual"
weight = 510

# Display
featured = false
recommended = false

# Publication Control
draft = false
layout = "page"
github_edit = true

# Advanced SEO
seo_type = "TechArticle"
seo_image = "multiple-languages-alpha-docs-seo.png"
+++
To enable Alpha's multilingual features, ensure **at least two languages** are defined in `languages.toml`

## Set Up Multiple Languages

To do that, edit the `config/_default/languages.toml` configuration file.
By default, it contains only the English language block:
```toml
[en]
  languageName = "English"
  languageCode = "en"  
  weight = 1
```
If, for example, you want to use only Spanish and Italian, you must add the corresponding language blocks:

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
**Note**: See the [language.toml documentation](/docs/config/languages-toml/) for more details.

## Creating Content in the New Languages
Alpha is tested and recommends **filename-based translation** and **not** language directories. To inform Hugo of the language used in a page, add the language code **before** the `.md` extension.

Here’s an example of a site with two sections and one page in each:
```toml
content/ 
├── articles/
│   ├── example-article/
│   │   └── index.md
│   └── _index.md
├── stories/
│   ├── example-story/
│   │   └── index.md
│   └── _index.md
└── _index.md
```
If you haven’t set `defaultContentLanguage` in `hugo.toml` config and your content files don’t use language suffixes, Hugo will use the language with the **lowest weight** as the default, in this case, Spanish.

However, **Alpha strongly recommends always using language suffixes**, even for the default language. This helps with **consistency** and **future flexibility**.

So your structure should be:
```toml
content/ 
├── articles/
│   ├── example-article/
│   │   └── index.es.md
│   └── _index.es.md
├── stories/
│   ├── example-story/
│   │   └── index.es.md
│   └── _index.es.md
└── _index.es.md
```
To translate a page, simply create another file with the **same name** but with a different language suffix:
```toml
content/ 
├── articles/
│   ├── example-article/
│   │   ├── index.es.md
│   │   └── index.it.md
│   ├── _index.es.md
│   └── _index.it.md
├── stories/
│   ├── example-story/
│   │   └── index.es.md <--- Missing index.it.md for stories/example-story
│   └── _index.es.md  <--- Missing _index.it.md for stories section
└── _index.es.md <--- Missing _index.it.md for homepage
```
In the above example every page that lacks a translation (all pages except `/articles/` and `example-article`) will have a **no translations** icon and the language switch will be disabled.

For pages that **do have translations** (like example-article), a language switch will appear with all available versions.

So the **only change** in how you [create your content](/docs/content-creation/) is the addition of the language code between the name and the extension `filename.[lang-code].md`.


###  Change slugs per language
The *filename* or *folder name* (for page bundles) must be the **same across all languages** so it's recommended to use English for consistency.

If you want to change the URL slug in a specific language, use the `slug` key in the  page’s frontmatter. 
 
For example, you won't rename `/example-article/` in Spanish or Italian. But if you want a different URL for the Italian version, you can add this to the frontmatter of `index.it.md`:
 ```toml
 slug = "esempio-articolo"
 ```
This will make the Italian URL `/articles/esempio-articolo`, while the Spanish version will remain at `/articles/example-article` unless you explicitly set a different slug for it as well.

