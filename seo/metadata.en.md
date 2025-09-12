+++
# Content Identity
title = "Metadata"
description = "Learn how to set the crucial SEO metadata for your pages in the Alpha Hugo theme."

# Authoring
author = "oxypteros"
date = "2025-09-12T14:15:34+02:00"
license = "CC-BY-SA"

# Organization
categories = ["SEO"]

## Series
series = "Alpha Docs"
parts = "SEO"
weight = 630

# Display
featured = false
recommended = false

# Publication Control
draft = false
layout = "page"
github_edit = true

# Advanced SEO
seo_type = "TechArticle"
seo_image = "metadata-alpha-docs-seo.png"
+++
Metadata are pieces of structured information in the `<head>` that describe the page content and settings to search engines, browsers, and social platforms.

Although they are not visible in the page body, their role is critical on how the page will be indexed, displayed in search results, and rendered across devices.

## Technical Metadata
The technical metadata for character encoding, alternate language, responsive design, and color scheme preferences are fully automated by Alpha, so you don’t need to configure them manually..

## SEO Metadata
The SEO focused metadata are set through the page’s frontmatter. The most important fields that **MUST ALWAYS** be filled are `title` and `description`.

### Title
The `<title>` (primary search snippet headline) is set by the `title = ""` key in the frontmatter. Hugo automatically includes it when generating the page.

### Description
The `<meta name="description" content="...">` (snippet description for SERPs) is set by the `description = ""` key.

{{< status_card TITLE="Attention" TYPE="warning" >}}

Because missing or incorrect values for title and description severely harm SEO, Alpha does not provide defaults. 
If left empty, [LiVa](docs/liva/) will warn you.

{{< /status_card >}}

## Best Practice

The title and description metadata can improve your search engine ranking and attract more clicks on your page. There’s no universal formula, since titles and descriptions depend heavily on your content. Still, the following tips work in most cases:

- **Keep it Concise**:
    - *Title:* Aim for 50-60 characters. Search engines cut off longer titles.
    - *Description:* Keep it under 160 characters to ensure the full text is visible in search results.
- **Be Descriptive**:
    - *Title:* Your title is a promise. It should accurately summarize the page's content.
    - *Description:* The description is an advertisement for your page. It should be compelling, relevant and of course descriptive. It should expand on the title, and encourage users to click.
- **Make it Unique**:
    - Avoid using the same title and description for multiple pages. Every page should have unique metadata that is specific to its content.