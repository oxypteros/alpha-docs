+++
draft = false
date = "2025-05-30T16:29:11+02:00"
lastmod = ""
layout = "page"

title = "menus.toml"
author = "oxypteros"
license = "CC-BY-SA"
github_edit = true
series = "Alpha Docs"
  parts = "Config Files"
  weight = 140
categories = ["Configuration"]

recommended = false
featured = false
description = "Alpha theme menu configuration: Customize main/footer menus, add social links with icons, manage entries."
# SEO
seo_type = "TechArticle"
seo_image = "menus-toml-alpha-docs-seo.png"
+++
{{< status-card TITLE="Before you begin" TYPE="warning">}}

If you **didn't** use the **Alpha Starter Site**, copy the entire **config folder** (`themes/alpha/config/`) to your site's root directory before editing anything. 
This ensures that your changes are preserved and won’t be overwritten by future Alpha updates.

{{< /status-card>}}

## Overview
The `config/_default/menus.toml` file defines and populates all menu entries used in Alpha.

Alpha supports six specific menu identifiers: 
- `[[main]]`, `[[main_secondary]]`, `[[main_social]]` --- used in the **hamburger menu** 
- `[[footer]]`, `[[footer_social]]` --- used in the **footer** 
- `[[sc_social]]` --- used in the social shortcode.

## Usage

### Menu Entry Format
```toml
# Menus
[[main]]          # Menu identifier        
  name = "Home"   # Menu entry
  url = "/"       # URL for the menu entry
  weight = 100    # Priority weight

# Social Menus
[[main_social]]                # Menu identifier
  name = "Github"              # Social name
  url = "https://github.com/"  # URL for the social entry
  pre = "#github"              # Icon for the social network
  weight = 100                 # Priority weight
```
**Note:** Menu identifiers are hardcoded, **do not** rename or alter them.

To disable a menu entry, either delete its keys or comment out the entire block:
```toml
# This entry will not render  
# [[main]]               
#  name = "Home"   
#  url = "/"       
#  weight = 100    
``` 
### Social Menus
The `pre` key determines the icon shown for a social network.
If `pre` is omitted or contains an invalid value, the `name` key value is used instead.
#### Valid values:
```toml
# Social icon values
  pre = "#instagram"
  pre = "#tiktok"
  pre = "#twitter"
  pre = "#youtube"
  pre = "#facebook"
  pre = "#twitch"
  pre = "#reddit"
  pre = "#pinterest"
  pre = "#linkedin"
  pre = "#discord"
  pre = "#snapchat"
  pre = "#telegram"
  pre = "#bluesky"
  pre = "#mastodon"
  pre = "#github"
  pre = "#gitlab"
  pre = "#bitbucket"
```
### Multilingual Menus
If your site is **multilingual** or your main language is **not English**, you’ll need to:
- Add translated versions of the `menus.toml` file, or
- Translate the default one for each language.

Otherwise, `menus.toml` will be used as a fallback.

To localize menus:
1. Copy `menus.toml`
2. Rename it to `menus.[language_code].toml`
3. Translate the **values** only, **do not** change the keys.

**Note:** The `[language_code]` must match the [section language code](/docs/config/languages-toml/#keys-reference) defined in `languages.toml`.

**Example:**
```toml
# languages.toml
[fr]
  weight = 2
  languageName = "French"
  languageCode = "fr-CA"

# menus.fr.toml 
[[main]]              
  name = "Accueil"  
  url = "/"       
  weight = 100
```
## Best Practices
- The original intent behind the menu design is to use `[[main_secondary]]` and `[[footer]]` for *"utility pages"* such as *Policy*, *About*, *Contact*, and similar entries.
- All menus are optional. Use only as many as your project requires.
- There is **no hardcoded limit** to the number of entries, but too many entries or long name values may visually break the layout.

## Keys Reference
name
: `name = "Example"`--- (**string**, optional)
: Display name of the menu entry.

url
: `url = "/posts/example"` --- (**string**, optional)
: URL for the menu entry. Both relative and absolute URLs are supported.

weight 
: `weight = 100` --- (**integer**, optional)
: Sets the order of the menus entries. Lower values appear first. 

pre
: `pre = "#github"` --- (**string**, optional)
: Displays a social network icon.  Must use a predefined value from the list above. 
: Used only in `[[main_social]]`, `[[footer_social]]`, `[[sc_social]]`
