+++
draft = false
date = "2025-05-31T14:23:15+02:00"
lastmod = ""
layout = "page"

title = "Text Content"
author = "oxypteros"
license = "CC0"
github_edit = true
series = "Alpha Docs"
  parts = "Shortcodes"
  weight = 230
categories = ["Shortcodes"]

recommended = false
featured = false
description = "Documentation for Alpha's text content Closed shortcode. Allows embedding styled Markdown content directly into any page layout. Supports inner content."
+++
## Example:
{{< text-content-example>}}
## Peer into the Shadows
I'm *John Smith*, your guide into the complex world of **true crime**. Here, we delve deep into compelling cases from haunting cold files to landmark investigations that shaped history. My focus is on *meticulous research*, *respecting the victims*, and exploring the often *unsettling questions left unanswered*.

### Unraveling Chilling Cases and Seeking Hidden Truths
If you **share** a fascination for uncovering hidden details and understanding the darker facets of humanity, you've found your space. 

This blog 
- examines the evidence, 
- explores the psychology, 
- and searches for truth within the shadows. 

Explore the archives, and let's investigate together.
{{< /text-content-example >}}

## Code
``` go-html-template
{{</* text-content */>}} 
## Peer into the Shadows
I'm *John Smith*, your guide into the complex world of **true crime**. Here, we delve deep into compelling cases from haunting cold files to landmark investigations that shaped history. My focus is on *meticulous research*, *respecting the victims*, and exploring the often *unsettling questions left unanswered*.

### Unraveling Chilling Cases and Seeking Hidden Truths
If you **share** a fascination for uncovering hidden details and understanding the darker facets of humanity, you've found your space. 

This blog 
- examines the evidence, 
- explores the psychology, 
- and searches for truth within the shadows. 

Explore the archives, and let's investigate together.
{{</* /text-content */>}}
```
### Overview
A **closed shortcode** that renders styled text content using Markdown.

### Usage
- Intended for inserting **text content** between other shortcodes on pages **not** originally designed to have styled text content, such as the *homepage* or *section pages*.
- Use this shortcode on the **homepage** and/or **section pages** (i.e. `_index.md`).
- This shortcode **requires** both opening and closing tags.

### Parameters Reference
Inner Content
: The main body of text displayed by the shortcode. Supports Markdown formatting. 

### Error Reporting
- This shortcode does not produce error reports.