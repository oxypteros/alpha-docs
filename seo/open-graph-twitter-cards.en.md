+++
# Content Identity
title = "Open Graph & Twitter Cards"
description = "Control how your pages look when shared on social platforms with Alpha’s built-in OpenGraph and Twitter card support."

# Authoring
author = "oxypteros"
date = "2025-09-13T16:48:29+02:00"
license = "CC-BY-SA"

# Organization
categories = ["SEO"]

## Series
series = "Alpha Docs"
parts = "SEO & SMO"
weight = 650

# Display
featured = false
recommended = false

# Publication Control
draft = false
layout = "page"
github_edit = true

# Advanced SEO
seo_type = "TechArticle"
seo_image = "smo-alpha-docs-seo.png"
+++
For **Social Media Optimization** (*SMO*), Alpha automatically generates **OpenGraph** and **Twitter cards** for each page.  

Both determine how your content will appear when it’s shared on social platforms, ensuring consistent and accurate previews.

{{< status_card TITLE="A Single Image for All Platforms" TYPE="info" >}}

Both **OpenGraph** and **Twitter Cards** use the same image, controlled by the `seo_image = ""` frontmatter key (or the global `seo_default_image = ""` in your `config/_default/params.toml`).

- **Recommended Dimensions:** `1200×630px`
- Alpha will automatically resize images to this standard when possible. If an image has a different aspect ratio, the original will be used, and **LiVa** will alert you during local development.

{{< /status_card >}}

## OpenGraph
Like [Schema](/docs/seo/schema/), OpenGraph is populated by frontmatter values. Simply fill the appropriate keys your content needs, and Alpha will generate the OpenGraph for your page.  

A complete generated OpenGraph example for a content page looks like this:

```html
<meta property="og:title" content="[Page Title]" />
<meta property="og:description" content="[Page Description]" />
<meta property="og:url" content="[Page URL]" />
<meta property="og:site_name" content="[Site Title]" />
<meta property="og:type" content="[website or article]" />
<meta property="article:author" content="[Page Author URL]" />
<meta property="article:published_time" content="[Published Date]" />
<meta property="article:modified_time" content="[Modified Date]" />
<meta property="og:locale" content="[Language]" />
<meta property="og:locale:alternate" content="[Alternate Language]" />
<meta property="og:image" content="[SEO Image]" />
<meta property="og:image:width" content="1200" />
<meta property="og:image:height" content="630" />
```
{{< status_card TITLE="Article Author" TYPE="info" >}}

In OpenGraph, the `article:author` value should **not** be the author name but the **URL** of the author’s profile on a social platform (usually *Facebook* or *LinkedIn*).

Add your social profile page URL to `seo_author_url = ""` in `config/_default/params.toml`, or override it per page with a `seo_author_url = ""` key in the frontmatter.

{{< /status_card >}}

## Twitter Cards
Twitter Cards are used exclusively when your page is shared on **X**.

Values are also filled by the corresponding frontmatter keys.

- If a `seo_image` is defined, a `summary_large_image` card is used.
- If not, a `summary` card is used.

A complete generated Twitter card (with image) looks like this:


```html
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:image" content="[SEO Image]">
<meta name="twitter:url" content="[Page URL]" />
<meta name="twitter:title" content="[Page Title]" />
<meta name="twitter:description" content="[Page Description]" />
<meta name="twitter:site" content="@[Twitter Username]" />
<meta name="twitter:creator" content="@[Twitter Username]" />
```
{{< status_card TITLE="Site/Creator" TYPE="info" >}}

For single-author sites, set `seo_twitter_username = ""` in `config/_default/params.toml` and both `twitter:site` and  `twitter:creator` will be populated automatically. 

To override only the `twitter:creator` value for a specific page, add `seo_twitter_username = ""` to that page’s frontmatter.

{{< /status_card >}}