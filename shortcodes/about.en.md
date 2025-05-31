+++
draft = false
date = "2025-05-31T16:16:18+02:00"
lastmod = ""
layout = "page"

title = "About"
author = "oxypteros"
license = "CC0"
series = "Alpha Docs"
  parts = "Shortcodes"
  weight = 280
categories = ["Shortcodes"]

recommended = false
featured = false
description = "Documentation for Alpha's about shortcode. Display minimal author info with an avatar, name, and Markdown biography text."
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
- Place the avatar image inside `/assets/img/` and set its filename (`filename.jpg`) as the value for the `AVATAR` parameter. The image will be resized and converted to WebP.
- If the `AUTHOR` parameter is omitted, the `author` value of the page will be used.
- This shortcode **requires both** an opening and a closing tag

### Parameters Reference
AUTHOR 
: `AUTHOR="Username"` --- (**string**, optional) 
: The author name. Fallback to page frontmatter author. 

AVATAR
: `AVATAR="image.jpg"` --- (**string**, optional) 
: Filename (**including extension**) of the avatar image, placed at `/assets/img/`. 

Inner Content 
: The main biography text. Markdown formatting supported.

### Error Reporting
- Warnings are printed to the Hugo terminal.
- OCD enabled.

#### Error Codes
ocd-sc-161
: Unrecognized parameter detected.

ocd-sc-162
: Image not found. Check filename in `/assets/img/` path.
