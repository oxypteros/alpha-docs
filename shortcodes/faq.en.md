+++
draft = false
date = "2025-05-31T16:07:43+02:00"
lastmod = ""
layout = "page"

title = "Frequently Asked Questions"
author = "oxypteros"
license = "CC0"
series = "Alpha Docs"
  parts = "Shortcodes"
  weight = 270
categories = ["Shortcodes"]

recommended = false
featured = false
description = "Learn to use Alpha's frequently Asked Questions shortcode. Format simple text FAQs with H2 questions & paragraph answers. Includes title/subtitle options & usage guide."
+++
## Example
{{< faq-example
TITLE="Frequently Asked Questions"
SUBTITLE="The last sight of the last donut!"
>}}
## When and how did the *"Last Donut"* disappear?
 It vanished from the breakroom box between **9:05** and **9:37**. There were no signs of struggle, no witnesses, and no note left behind.

 ## Any suspects or leads in the donut disappearance?
 *Brenda* and *Dave* were nearby but have [alibis](#example) (sort of). The lack of crumbs is suspicious, suggesting careful removal or off-site consumption. Motive is unknown.

 ## What's so baffling about the *"Last Donut"* case?
 The sheer audacity and efficiency of the act are staggering. The complete lack of physical evidence, *(no sticky residue, no dropped sprinkles, no crumbles)*  suggests a level of planning inconsistent with a simple crime of passion (or hunger). 
 It begs the question: 
 [Was this a planned operation, or an incredibly lucky, impulsive grab?](#example)
 The mystery endures.
{{< /faq-example >}}

## Code
```go-html-template
{{</* faq
TITLE="Frequently Asked Questions"
SUBTITLE="The last sight of the last donut!"
*/>}}
## When and how did the *"Last Donut"* disappear?
It vanished from the breakroom box between **9:05** and **9:37**. There were no signs of struggle, no witnesses, and no note left behind.

## Any suspects or leads in the donut disappearance?
*Brenda* and *Dave* were nearby but have [alibis](/posts/the-last-donut#alibi) (sort of). The lack of crumbs is suspicious, suggesting careful removal or off-site consumption. Motive is unknown.

## What's so baffling about the *"Last Donut"* case?
The sheer audacity and efficiency of the act are staggering. The complete lack of physical evidence, *(no sticky residue, no dropped sprinkles, no crumbles)*  suggests a level of planning inconsistent with a simple crime of passion (or hunger). 
It begs the question: 
[Was this a planned operation, or an incredibly lucky, impulsive grab?](/posts/the-last-donut)
The mystery endures.
{{</* /faq */>}}
```
### Overview
A lightweight **Frequently Asked Questions (FAQ)** shortcode, featuring a **title** and an optional **subtitle**. Designed for simple, text-based question and answer blocks.

### Usage
- Format each FAQ entry by writing a question as an **H2 heading** (`##`) followed immediately by the corresponding answer **without inserting empty lines**.
- Supported formatting inside answers includes **bold**, *italic*, and [links](#).  
- Lists, blockquotes, images, or any other Markdown elements **not** enclosed within the first paragraph after the H2 heading are not rendered.
- This shortcode **requires both** an opening and a closing tag

### Parameters Reference
TITLE 
: `TITLE="Example title"` --- (**string**, optional) 
: H2 heading.

SUBTITLE
: `SUBTITLE="Example subtitle"` --- (**string**, optional) 
: H3 heading.

Inner Content 
: H2 headings are rendered as questions, and the first following `<p>` element is rendered as the answer. Supports Markdown styling only if enclosed within the paragraph.

### Error Reporting
- Warnings are printed to the Hugo terminal.
- OCD enabled.

#### Error Codes
ocd-sc-151
: Unrecognized parameter detected.
