+++
# Content Identity
title = "About Shortcode"
description = "Documentation for Alpha's about shortcode. Display minimal author info with an avatar, name, and Markdown biography text."

# Authoring
author = "oxypteros"
date = "2025-05-31T16:16:18+02:00"
lastmod = "2025-07-14T10:45:29+02:00"
license = "CC-BY-SA"

# Organization
categories = ["Shortcodes"]

## Series
series = "Alpha Docs"
parts = "Shortcodes"
weight = 280

# Display
featured = false
recommended = false

# Publication Control
draft = false
layout = "page"
github_edit = true

# Advanced SEO
seo_type = "TechArticle"
seo_image = "about-shortcode-alpha-docs-seo.png"
+++
## Example:

{{< about-example AUTHOR="John Smith" AVATAR="oxy.png" >}}

 The researcher and writer behind this blog. Driven by a deep fascination with the complexities of criminal cases and the quest for **truth**. 
 
 Join me in the quest to meticulously piecing together stories, analyzing evidence, and exploring the unanswered questions that linger long after the headlines fade.
 
 ***The truth is here!*** *(not out there)*

{{< /about-example >}}

## Code
```go-html-template
{{</* about AUTHOR="John Smith" AVATAR="oxy.png" */>}}

 The researcher and writer behind this blog. Driven by a deep fascination with the complexities of criminal cases and the quest for **truth**. 
 
 Join me in the quest to meticulously piecing together stories, analyzing evidence, and exploring the unanswered questions that linger long after the headlines fade.
 
***The truth is here!*** *(not out there)*

{{</* /about */>}}
```
### Overview
A minimal **About the Author** element with avatar, name, and bio text.

### Usage
- Place the avatar image inside `assets/img/` and set its filename (`filename.jpg`) as the value for the `AVATAR` parameter. The image will be resized and converted to WebP.
- If the `AUTHOR` parameter is omitted, the `author` value of the page will be used.
- This shortcode **requires both** an opening and a closing tag

### Parameters Reference
AUTHOR 
: `AUTHOR="Username"` --- (**string**, optional) 
: The author name. Fallback to page frontmatter author. 

AVATAR
: `AVATAR="image.jpg"` --- (**string**, optional) 
: Filename (**including extension**) of the avatar image, placed at `assets/img/`. 

Inner Content 
: The main biography text. Markdown formatting supported.


#### Error Codes
liva-sc-200
: Unrecognized parameter detected.

liva-sc-209
: Image not found. Check filename in `assets/img/` path.
