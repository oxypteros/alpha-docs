+++
draft = false
date = "2025-05-30T16:19:05+02:00"
lastmod = ""
layout = "page"

title = "languages.toml"
author = "oxypteros"
license = "CC-BY-SA"
github_edit = true
series = "Alpha Docs"
  parts = "Config Files"
  weight = 130
categories = ["Configuration"]

recommended = false
featured = false
description = "Alphas languages.toml documentation: Define supported languages, set their display order and names for your Alpha Hugo site, and understand key configuration options."
# SEO
seo_type = "TechArticle"
seo_image = "languages-toml-alpha-docs-seo.png"
+++
{{< status_card TITLE="Before you begin" TYPE="warning">}}

If you **didn't** use the **Alpha Starter Site**, copy the entire **config folder** (`themes/alpha/config/`) to your site's root directory before editing anything. 
This ensures that your changes are preserved and won’t be overwritten by future Alpha updates.

{{< /status_card>}}

## Overview
The `config/_default/languages.toml` file defines the **languages** supported by your site and sets the **order** and **display name** for each. Alpha is **multilingual** ready.

## Usage
If your site is **multilingual** or your main language is **not** English, you need to declare the supported languages in the `languages.toml` file.

### Language Entry Format

```toml
[en]
  weight = 1
  languageName = "English"
  languageCode = "en"
```
To add a second language, for example Canadian French:
```toml
[en]
  weight = 1
  languageName = "English"
  languageCode = "en"

[fr]
  weight = 2
  languageName = "Français"
  languageCode = "fr-CA"
``` 
## Best Practices
Alpha uses **filename based** translation, **not** directories. To learn more about setting up a multilingual site with Alpha, refer to the [Multilingual documentation](/docs/multilingual/).

If multiple languages are found in `languages.toml` the language switch is activated.

## Keys Reference
- Each language key is defined under a section (*table*) with a language code (ex. `[en]`). 
- Only **two** or **three-letter** codes are valid here. 
- For *region* or *variants* of the language, use the `languageCode` key.

weight 
: `weight = 1` --- (**integer, recommended**)
: Sets the order of the languages. Lower values have priority. 

languageName
: `languageName = "English"` --- (**string, recommended**)
: Full display name of the language, shown in the language switch.
: If missing, triggers the `liva-lang-100` error.

languageCode 
: `languageCode = "en-US"`--- (**string**, optional)
: The IETF language tag used to define the content language for **browsers** and **search engines**.
: Can be a simple two-letter code (`en`), a language-region pair (`fr-CA`), or a more specific form like `hy-Latn-IT-arevela`. For valid formats and examples, refer to [RFC 5646 Appendix A.](https://datatracker.ietf.org/doc/html/rfc5646#appendix-A)
: If omitted, the language code from the section will be used. 
