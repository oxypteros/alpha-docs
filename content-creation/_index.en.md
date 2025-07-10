+++
draft = false
date = "2025-06-02T17:59:29+02:00"
lastmod = ""
layout = "list"
paginate = false

title = "Content Creation"
author = "oxypteros"
license = "CC-BY-SA"
series = "Alpha Docs"
  weight = 410
description = "Alpha theme content creation guide: Understand archetypes, organize your content into sections and pages, and explore layout flexibility. Includes helpful FAQ."
# SEO
seo_type = "TechArticle"
seo_image = "content-creation-alpha-docs-seo.png"
+++

{{< text_snippet TITLE="Unleash your Words" >}}

Alpha considers all pages **content**, from a *“boilerplate”* policy page to a *multichapter narrative*, Alpha aims to support an uninterrupted reading experience..  
Every layout is designed to provide a cohesive visual style while giving you the flexibility to create different types of text.

{{< /text_snippet>}}

{{< text_content>}}

## Archetypes
Alpha offers **frontmatter archetypes** specified for each layout, (`page`, `story`, `utility`, `home`, `list`, `taxonomy`, `terms`) and a `default` with only global keys.

To create a page using a specific archetype, use the command:
```bash
hugo new content --kind [archetype] [path]/filename.md
```
**Note:** Don't start the `[path]` with `/`.

### Creating Sections and Pages.
Each archetype corresponds to a layout: `page`, `story`, `utility`, `home`, `list`, `taxonomy`, `terms`.

Lets consider a site that has the following `content/` structure.
```
content/
├── articles/
│   └── _index.md
└── _index.md
```
We want to create a new **section** called **stories**:
```bash
hugo new content --kind list stories/_index.md
```
```
content/ 
├── articles/
│   └── _index.md
├── stories/
│   └── _index.md
└── _index.md
```
And then we create a **page bundle** titled "Example Story":
```bash
hugo new content --kind story stories/example-story/index.md
```
The final structure will be:
```
content/ 
├── articles/
│   └── _index.md
├── stories/
│   ├── example-story/
│   │   └── index.md
│   └── _index.md
└── _index.md
```
{{< /text_content>}}

{{< num_list TITLE="Let's Create" STYLE="card-list">}}

{{< faq TITLE="Questions no one asked" SUBTITLE="But I’m answering them anyway.">}}

## Can I use x layout for y content?
Yes, you’re free to use any layout as you see fit. However, each layout in Alpha was designed and tested for a specific purpose. Using a layout outside of its intended context and scope may result in unexpected behavior.
## What if there’s no layout for my content type?
If none of the available layouts suit your content, feel free to reach out with a detailed description of what you need. If it’s feasible, I’ll consider adding a new layout in a future version of Alpha. Of course, you’re also free to create your own custom layouts.
## Why doesn’t my page look like the demo?
Layouts in Alpha act as frames. The final result depends on your **frontmatter**, **shortcodes**, **Markdown** and of course **your content**. Carefully review the documentation for each page’s frontmatter options and the [shortcode section](/docs/shortcodes/). If something still seems off, feel free to contact me.
## I'm using layout x, but don’t want element y to appear.
Each layout includes specific elements to support its intended purpose. Some elements can be toggled from the frontmatter, while others are hardcoded. If an element isn't marked in the documentation as optional, it can't be disabled unless you duplicate and modify the layout manually.
## I disabled an optional element but get an error about it.
OCD errors exist to help you build an **optimal**, **semantically correct**, and **accessible** website. They **do not** affect the published site and are **not visible** to visitors so you are free to ignore them.
That said, if you choose to do so, be aware that your final page may lack one or more key elements, such as **metadata** or **semantic tags**, which may impact *SEO*, *accessibility*, or *general structure*.

{{< /faq >}}
