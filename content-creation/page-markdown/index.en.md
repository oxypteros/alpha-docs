+++
# Content Identity
title = "Page Markdown"
description = "Markdown demo for Alpha's page layout. See examples of headings, lists, links, images, code blocks, tables, and more, with Alpha specific notes"

# Authoring
author = "oxypteros"
date = "2025-06-03T14:45:36+02:00"
lastmod = "2025-07-14T13:53:46+02:00"
license = "CC-BY-SA"

# Organization
categories = ["Content"]
tags = ["markdown"]
## Series
series = "Alpha Docs"
parts = "Content Creation"
weight = 445

# Display
featured = false
recommended = false

# Publication Control
draft = false
layout = "page"
github_edit = true

# Advanced SEO
seo_type = "TechArticle"
seo_image = "page-markdown-alpha-docs-seo.png"
+++
## Overview
This is a demo page showcasing the markdown styles used in the **page layout** of Alpha.

The following elements are created strictly using **Markdown syntax**. Alpha also includes various **shortcodes** that extend or enhance these Markdown elements. Follow the link to learn more about [Alpha's shortcodes](/docs/shortcodes/ "Shortcode documentation for Alpha theme").

## Markdown Examples:

### Headings

## Heading H2

### Heading H3

#### Heading H4

##### Heading H5

###### Heading H6

```markdown
## Heading H2

### Heading H3

#### Heading H4

##### Heading H5

###### Heading H6
```

**Note**: The page title already uses an `<h1>` tag. Alpha automatically renders top-level content headings as `<h2>` to avoid duplicate `<h1>` tags.

### Emphasis

You can use *italics*, `*italics*`, for emphasis. You can also use **bold**,  `**bold**` for stronger emphasis. And of course you can combine both: ***bold and italic***, `***bold and italic***`.

Other styles that you can use for emphasis is the ==mark element== (`==mark element==`), highlights the selected text. The ~~del element~~ (`~~del element~~`), visually marks the text as deleted and respectively the ++ins element++ (`++ins element++`), marks text as added to the content.

###  Superscript & subscript
For *superscript*: Ca^2+^ (`Ca^2+^`), or *subscript*: H~2~SO~4~ (`H~2~SO~4~`), wrap the desired characters with `^` for superscript and `~` for subscript.


### Lists

#### Unordered Lists

-   Item one (`- Item one`)
-   Item two (`- Item two`)
-   Item three (`- Item three`)


#### Ordered Lists

1.  First item (`1. First item`)
1.  Second item (`1. Second item`)
1.  Third item (`1. Third item`)

#### Checklists

- [ ] First item to-do (`- [ ] First item to-do`)
- [x] Second item to-do (`- [x] Second item to-do`)
- [ ] Third item to-do (`- [ ] Third item to-do`)

### Links

An absolute external link to [Hugo](https://gohugo.io/ "Title for external link to gohugo.io"), `[Hugo](https://gohugo.io/)`, and a relative [internal link](/docs/content-creation/page-markdown/#links "Title for internal link") to an anchor `[internal link](/docs/content-creation/page-markdown/#links)`.

You can add an optional title, which appears when hovering over the link, by placing it inside quotes after the URL: `[Hugo](https://gohugo.io/ "This is the title")`.

**Note**: Any link that starts with `http` will open in a new tab (`target="_blank"`) and include `rel="noopener noreferrer"` for security. Internal links (`#anchor` or `/relative-path/`) remain unaffected.

### Blockquotes

> This is a blockquote.  
> Blockquotes are useful for quoting someone or highlighting important information.

To create a blockquote, simply place a `>` before the text `> This is a blockquote`

### Horizontal Rule

A horizontal rule is used to separate content:

---

Use three dashes (`---`) on a **new line**[^1] to insert a horizontal rule.

### Description Lists
With the description lists `<dl>` you can create lists with **terms** and **descriptions** (key-value pairs).

To create a description list, follow this format:

```markdown
Term 1
: Description of Term 1

Term 2
: Description of Term 2

Term 3
: Description of Term 3
```
For example 

Html
: The standard markup language for creating web pages.

Tailwind
: A utility-first CSS framework 

Javascript
: A programming language that enables interactive web pages.

Hugo 
: A fast and modern static site generator (SSG) written in Go.

```markdown
Html
: The standard markup language for creating web pages.

Tailwind
: A utility-first CSS framework 

Javascript
: A programming language that enables interactive web pages.

Hugo 
: A fast and modern static site generator (SSG) written in Go.
```
You can also associate multiple descriptions with a single term:

Alpha was built with
: Html
: Tailwind
: Javascript
: Hugo

```markdown
Alpha was build with
: Html
: Tailwind
: Javascript
: Hugo
```
**Note**: Description lists provide **semantic** meaning, which can **improve accessibility** and, **indirectly, SEO**. Screen readers can use the `<dl>`, `<dt>`, and `<dd>` tags to provide a more structured experience for users.

### Image

Alpha automatically serves **optimized**, **responsive** images in **WebP** format, if they are:
- Inside a [page bundle](https://gohugo.io/content-management/page-bundles/ "Hugo page bundles documentation") 
- In the `assets/img/` folder or 
- From a remote location, example `https://example.com/image.jpg`.  


![A close up photo of a German Shepherd puppy ](pexels-cynthia-vh-729026-1572849.jpg "Photo by Cynthia Vh")

To add an image in your article, place your original image inside the **page bundle** folder of the article or in the `assets/img/` folder and then add the markdown code:
`![Description of the photo](filename.jpg "Optional caption")`

For an image from a remote location add the absolute URL of the image:
`![Description of the photo](https://example.com/image.jpg "Optional caption")`

**Note**: The *"Description of the photo"*, becomes the `<alt>` attribute for accessibility. The *"Optional caption"* is used as the `<figcaption>`. 
Recommended photo size: **width > 710px**.


### Code

For inline code, enclose your code snippet with backticks: <code>\`const greeting = "Hello, world!";\`</code>.

For multi-line code blocks, use triple backticks: 

``````markdown
  ```javascript
  function greet(name) {
    console.log(`Hello, ${name}!`);
  }

  greet("World");
  ```
``````

And will render as:


```javascript
function greet(name) {
  console.log(`Hello, ${name}!`);
}

greet("World");
```
**Note**: You can specify the language for the code block after the opening backticks <code>```language_name</code>. Follow the link to see the complete list of [supported languages](https://gohugo.io/content-management/syntax-highlighting/#languages "Hugo syntax highlighting supported languages") 


### Tables

To create a table, use the following code:

```markdown
| Header 1 | Header 2 | Header 3 | Header 4 |
| -------- | -------- | -------- | -------- | 
| Cell 1/1 | Cell 1/2 | Cell 1/3 | Cell 1/4 | 
| Cell 2/1 | Cell 2/2 | Cell 2/3 | Cell 2/4 | 
| Cell 3/1 | Cell 3/2 | Cell 3/3 | Cell 3/4 | 
```

| Header 1 | Header 2 | Header 3 | Header 4 |
| -------- | -------- | -------- | -------- | 
| Cell 1/1 | Cell 1/2 | Cell 1/3 | Cell 1/4 | 
| Cell 2/1 | Cell 2/2 | Cell 2/3 | Cell 2/4 | 
| Cell 3/1 | Cell 3/2 | Cell 3/3 | Cell 3/4 | 



### Footnote
To create a footnote in Markdown, you need two parts:

- A footnote **reference** (inline marker in the text).
- A footnote **definition** (the actual footnote content).

1. Adding a Footnote Reference
Place a reference next to the word you want to footnote: `word[^example]`. 
Each footnote reference should have a unique *trigger* to avoid accidentally linking multiple references to the same footnote. 
1. Defining the Footnote
At the end of your article (or a designated footnote section), add `[^example]:` and after the actual footnote content.
The colon (`:`) is required, it **separates** the footnote **reference** from the footnote **definition**.

A footnote example[^demo]. (`example[^demo]`)

**Note**: 
- Markdown automatically numbers footnotes **sequentially** (regardless of reference names).
- Adds a horizontal rule (`<hr>`) before footnotes.
- Links references to their definitions for easy navigation.

**Attention**:
- The footnote **reference** and **definition** must **match EXACTLY**.
- If the definition is missing or mismatched, the footnote will not appear.

[^1]: If the three dashes are **not** in a new line will render an em dash --- and not a `<hr>`

[^demo]: This is the footnote content. (`[^demo]: This is the footnote content.`)