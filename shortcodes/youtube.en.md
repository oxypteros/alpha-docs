+++
# Content Identity
title = "YouTube Shortcode"
description = "An Alpha Shortcode that embeds a privacy and performance-focused YouTube video."

# Authoring
author = "oxypteros"
date = "2025-09-16T16:37:38+02:00"
license = "CC-BY-SA"

# Organization
categories = ["Shortcodes"]

## Series
series = "Alpha Docs"
parts = "Shortcodes"
weight = 300

# Display
featured = false
recommended = false

# Publication Control
draft = false
layout = "page"
github_edit = true

# Advanced SEO
seo_type = "TechArticle"
seo_image = "youtube-shortcode-alpha-docs-seo.png"
+++
## Example: 

{{< youtube TITLE="The Dead South - In Hell I'll Be In Good Company " VIDEO-ID="B9FzVhw8_bY" >}}

## Code
``` go-html-template
{{</* youtube TITLE="The Dead South - In Hell I'll Be In Good Company " VIDEO-ID="B9FzVhw8_bY" */>}} 

```
### Overview
Embeds any public YouTube video on your page with a strong focus on **performance** and **privacy**.

This shortcode uses the lightweight [lite-youtube-embed](https://github.com/paulirish/lite-youtube-embed) facade, which defers loading the full player until the user clicks Play. This ensures optimal page speed and performance.


{{< status_card TITLE="Local Development" TYPE="info" >}}

When testing the shortcode locally on `http://localhost`, you may sometimes notice that the video doesn’t load on the first click and shows a browser privacy error.  

This is **normal** and **expected** when developing locally.  

It happens because browsers apply strict security rules when loading secure (`https://`) content like the YouTube player from an insecure (`http://`) page such as your dev environment.  

- Simply go back and click the play button again, the video will usually load fine on the second try.  
- For a smoother experience, you can run your localhost with SSL using a tool like [mkcert](https://github.com/FiloSottile/mkcert).  

This is a **development-only issue** and can be safely ignored.  
On your live website (served over `https://`), it will never occur.

{{< /status_card >}}

### Usage
You must provide the unique **YouTube video ID** for the shortcode to work.

The video ID is the unique **11-character** string in the video’s URL (`https://www.youtube.com/watch?v=[VIDEO_ID]`)

**Example:** For the following URL

```html
https://www.youtube.com/watch?v=B9FzVhw8_bY&list=RDB9FzVhw8_bY&index=2
```
the video ID is:

```
VIDEO-ID="B9FzVhw8_bY"
```
### Privacy
The Alpha theme is designed to be a **privacy-first** platform. The `youtube` shortcode upholds this principle:

- **No Cookies on Load:** Visiting a page with an embedded video **does not** set any cookies.
- **Consent by Interaction:** Only when a visitor explicitly clicks **"Play"** does YouTube load its player and set its own cookies.

For full transparency, we recommend adding a brief note to your site’s privacy policy regarding this behavior.

### Parameters Reference
TITLE
: `TITLE="Example Title"` --- (**string**, optional) 
: A descriptive title for the video, displayed as a `<figcaption>` below the player.

VIDEO-ID
: `VIDEO-ID="B9FzVhw8_bY"` --- (**string**, **required**)
: The 11-character YouTube video ID.
: LiVa error if is missing.

#### Error Codes
liva-sc-230
: Unrecognized parameter detected.

liva-sc-235
: The `VIDEO-ID` parameter was not provided or was left empty.
