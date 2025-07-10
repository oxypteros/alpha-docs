+++
draft = false
date = "2025-05-30T19:11:30+02:00"
lastmod = ""
layout = "list"
paginate = false

title = "Shortcodes"
author = "oxypteros"
license = "CC-BY-SA"
series = "Alpha Docs"
  weight = 180
description = "Discover Alpha theme's shortcodes. Learn how they empower you to design, enrich, and customize your site, all without touching a line of theme code."
# SEO
seo_type = "TechArticle"
seo_image = "shortcodes-alpha-docs-seo.png"
+++
 
{{< text_snippet >}}

In Alpha shortcodes play a crucial role. They not only enhance your content beyond Markdown's limitations but also let you design and customize your site.

{{< /text_snippet>}}

{{< text_content >}}

## Overview
In Alpha, many of the **key components** used to structure and enrich a webpage are provided as shortcodes.

This may introduce a small learning curve before you start producing content, but in return, you gain flexibility:  
- You're **not locked into hardcoded layouts**.  
- You **don’t need to edit theme files** to personalize your content.  

All Alpha shortcodes:
- Follow the design philosophy of Alpha.
- Integrate seamlessly with the layout system.
- Are fully supported by **OCD**, Alpha’s built-in helper.

Because shortcodes are so central to how Alpha works, their documentation is presented early.  
Feel free to **skim through** now to get a rough idea, then **come back when you actually need one**.

> If you’re new to Hugo or shortcodes in general, don’t worry, just copy the examples when needed.

{{< /text_content >}}

{{< num_list TITLE="Shortcode List" STYLE="card-list">}}

{{< faq TITLE="Questions no one asked" SUBTITLE="But I’m answering them anyway.">}}

## Do shortcodes work in any layout?
Yes, Alpha's shortcodes are layout agnostic within Alpha. However, some are designed with specific contexts in mind. For example, the featured shortcode is intended as one of the first components of the homepage, and while it will technically work on all pages, it will look visually out of place.
If the shortcode documentation recommends a specific use case, it's best to follow it for optimal results.

## Can I use a shortcode from another theme?
Technically yes, but it probably won’t integrate well with Alpha.  
Shortcodes aren’t always theme-agnostic.  While they’re all written in Hugo’s templating language, most are built with a specific theme’s styles and structure in mind. With some effort, you can make them work but expect layout issues or styling mismatches.

## I want to use an element that doesn’t exist as a shortcode. What now?
Just ask! If the feature makes sense for Alpha and is doable, I’ll consider adding it in a future release.

{{< /faq >}}