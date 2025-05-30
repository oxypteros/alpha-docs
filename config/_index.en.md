+++
draft = false
date = "2025-05-30T13:41:16+02:00"
lastmod = ""
layout = "list"
paginate = false

title = "Configuration Files"
series = "Alpha Docs"
  weight = 110
description = "Alpha theme configuration documentation. Customize global settings, understand options in hugo.toml and Alpha Specific in params.toml."
+++
{{< text-snippet >}}
My initial goal for Alpha was to use as few Alpha **specific configuration** keys as possible.
While I can’t say that goal was fully achieved, I believe I avoided unnecessary complexity without compromising Alpha’s customization features.
{{< /text-snippet >}}

{{< text-content>}}
## Overview
The main configuration files of Alpha are located in the `config/` folder inside Alpha's theme folder `/themes/alpha/config/_default`:
``` bash
config/_default/
├── hugo.toml
├── languages.toml
├── menus.toml
└── params.toml
```
**Note**: Alpha also includes a `hugo.toml` file at the root of the theme. This serves only as a **template**.

To safely customize Alpha without risking your changes being overwritten during updates, it’s highly recommended to copy the default theme configuration from:
```bash
themes/alpha/config/_default
```
...into your site’s root:
```bash
config/
```
This way, Hugo will use your locals version values, and future Alpha updates won’t override your settings.

**Note:** If you’re using Alpha as a **Hugo module**, you can download a pre-packaged version of the config folder here:[Download Alpha Config](/downloads/config.zip "alpha-download")

## Attention: Avoid Config Merging Issues
If your project already has a complex setup with:
- A populated `config/_default/` folder, or
- A large, root-level `hugo.toml`

**Do not merge files blindly!!!**. 

1. Instead backup/rename your original files:
```bash
mv config/_default config/_default.old
mv hugo.toml hugo.toml.old

```
2. Copy Alpha’s config folder to your root `config/`:
```bash
cp -r themes/alpha/config/_default config/

```
3. **Carefully integrate any custom values** you had in your old config.
4. **Test** your site thoroughly before deploying.
{{< /text-content>}}

{{< num-list TITLE="Config Files" STYLE="card-list">}}
{{< faq TITLE="Questions no one asked" SUBTITLE="But I’m answering them anyway.">}}
## Can I use Hugo's default configuration keys in hugo.toml?
Hugo is an extensive and potentially complex ecosystem. It's nearly impossible to test every possible configuration. You can use any setting that enhances your site, but be sure to thoroughly **test for conflicts** with Alpha’s defaults before deploying to production.

## I don't like TOML. Can I use another format?
Alpha uses **TOML exclusively** because I find it beginner friendly, with clear, readable **key value pairs**.
If you prefer YAML or JSON, you’ll need to manually adapt Alpha's config files to your desired format.
{{< /faq >}}