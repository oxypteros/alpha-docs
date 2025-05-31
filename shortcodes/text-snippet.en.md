+++
draft = false
date = "2025-05-31T13:01:01+02:00"
lastmod = ""
layout = "page"

title = "Text Snippet"
author = "oxypteros"
license = "CC0"
github_edit = true
series = "Alpha Docs"
  parts = "Shortcodes"
  weight = 210
categories = ["Shortcodes"]

recommended = false
featured = false
description = "Documentation for the Alpha's text-snippet closing shortcode. Learn to add centered text blocks with optional titles using Markdown content. Params & usage."
+++
## Example
{{< text-snippet-example TITLE="No Crime Too Small, No Clue Too Crumbly">}}
Whether it's a *cold case* that's haunted generations or the *baffling disappearance* of the office's last donut, we believe every puzzle deserves to be solved. 
Join us as we meticulously **examine** the evidence, **interrogate** the unusual, and **bring closure**, one bizarre case at a time.  
{{< /text-snippet-example >}}

## Code
``` go-html-template
{{</* text-snippet TITLE="No Crime Too Small, No Clue Too Crumbly" */>}} 
Whether it's a *cold case* that's haunted generations or the *baffling disappearance* of the office's last donut, we believe every puzzle deserves to be solved. 
Join us as we meticulously **examine** the evidence, **interrogate** the unusual, and **bring closure**, one bizarre case at a time. 
{{</* /text-snippet */>}}
```
### Overview
A closed shortcode that renders a centered text snippet with an optional title.

### Usage
- Designed for use as a text separator or section introduction.
- Can be used on any page.
- This shortcode **requires** both opening and closing tags.

### Parameters Reference
TITLE
: `TITLE="Example Title"` --- (**string**, optional) 
: H2 heading, centered above the snippet.

Inner Content 
: The main body of text. Supports Markdown formatting. 

### Error Reporting
- Warnings are printed to the Hugo terminal.
- OCD enabled.

#### Error Codes
ocd-sc-111
: Unrecognized parameter detected.
