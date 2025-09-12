+++
# Content Identity
title = "Install Alpha"
description = "Learn how to install the Alpha Hugo theme. Instructions for fresh setups, adding to existing projects."

# Authoring
author = "oxypteros"
date = "2025-05-29T19:54:54+02:00"
lastmod = "2025-09-12T12:43:21+02:00"
license = "CC-BY-SA"

# Organization
categories = ["Get Started"]

## Series
series = "Alpha Docs"
parts = "Installation"
weight = 100

# Display
featured = false
recommended = false

# Publication Control
draft = false
layout = "page"
github_edit = true

# Advanced SEO
seo_type = "TechArticle"
seo_image = "install-alpha-docs-seo.png"
+++
{{< status_card TITLE="Prerequisites" TYPE="warning" >}}

1. To follow this guide, your system should have the following installed:  
    - **Hugo** (version **`0.146.1`**    or later)
    - A **terminal** (**PowerShell 7** on Windows)
    - A text editor.
2. Optional (*method-dependent*) you will need **Git**, a **GitHub account**, **Go**

If you're missing any of these or you're not sure what they are, start with the [Get Started: From Zero with Zero](/get-started/) guide.

{{< /status_card >}}

## Overview

To make things easier, I’ve divided the installation guide based on two use cases:
1. You want to **create a new Hugo site using Alpha**
2. You want to **add Alpha to an existing Hugo site**

Within each case, the methods are ordered from simplest to most advanced.

> **My recommendation:**
> Pick the method that makes the most sense to you. If you're just getting started, **simplicity** is more important than using the *"best"* or most complex method.

## Table of Content
- [Alpha for a new site](#alpha-for-a-new-site)
    1. [Manual Install](#method-i--manual-install)
    2. [Template](#method-ii--template)
- [Alpha for an existing site](#alpha-for-an-existing-site)
    1. [Read Me!](#read-me)
    2. [Manual Install](#method-i--manual-install-1)
    3. [Git Submodule](#method-ii--git-submodule)
    4. [Hugo Module](#method-iii--hugo-module-requires-go)
- [Troubleshoot](#troubleshoot)

## Alpha for a new site
If you're starting fresh, the easiest way to use Alpha is by using the [Alpha Starter](https://github.com/oxypteros/alpha-starter/). It’s a Hugo site that comes pre-configured to use the Alpha theme. No post-install configuration needed.

### Method I --- Manual Install 
1. Download the latest version of [Alpha Starter](/downloads/alpha-starter.zip "alpha-download")
2. Unzip the downloaded file.
3. Open your terminal and navigate into the unzipped folder:
```bash
cd alpha-starter
```
4. Start the Hugo development server:
```bash
hugo server
```
5. Open your browser to the local address shown in the terminal ([http://localhost:1313](http://localhost:1313) ) and begin customizing your site from your editor.

### Method II --- Template 
1. Go to the [Alpha Starter Github repository](https://github.com/oxypteros/alpha-starter/)
2. Click the green **"Use this template"** button and choose **"Create a new repository"**.
3. Name your new repo and click **"Create repository"**.
4. Open your terminal and clone your new repository:
```bash
git clone https://github.com/[YOUR_USERNAME]/[YOUR_REPOSITORY_NAME].git
```
5. Navigate into your cloned repository folder
```bash
cd YOUR_REPOSITORY_NAME
```
6. Start the Hugo server
```bash
hugo server
```
7. Open the site locally and start customizing.

### Not Recommended: Fork or Clone Directly
Avoid forking or directly cloning the alpha-starter repository into your project as-is unless you plan to:
- Remove the `.git` folder, and
- Reinitialize your own Git repository:
```bash
rm -rf .git
git init
```
Otherwise, your project will be tied to the Alpha Starter’s Git history, which will cause issues when pushing or pulling to your own repository.


## Alpha for an existing site
If you already have a Hugo site, chances are you’re familiar with themes and have one in use. This means installing Alpha should be straightforward and without surprises.

### Read Me!
Before we begin, there are **two important things to keep in mind** to ensure Alpha works smoothly with your existing setup:

1. **Configuration Files**
Alpha is designed with a **soft separation** between the **main Site Hugo configuration** (typically in `hugo.toml`) and **Alpha-specific configuration** (in `config/_default/`).
To avoid issues and keep your site clean:
    -  **Copy** the folder `themes/alpha/config/_default` into your root-level `config/` directory.
    - **Before you do this**, it’s highly recommended that you read the [Configuration Guide](/docs/config/) to avoid unpleasant surprises.
2. **Frontmatter Fields**
Just like your previous theme, Alpha uses a mix of **standard Hugo frontmatter keys** and some **theme-specific ones**.
To ensure a consistent look and behavior across your site after the Alpha installation:
    - Go through your existing content files and **update or add the front matter fields** required by Alpha.
    - This helps maintain a uniform visual style between your older content and any new content you’ll create with Alpha.
    - The required front matter keys are explained in the [Content Creation](/docs/content-creation/) 

### Method I --- Manual Install
> This method is easiest for quick tests or beginners.
1. [Download Alpha](/downloads/alpha.zip)
2. Unzip it into your site’s `themes/` folder so the structure is:
```bash
themes/alpha/
```
3. In your `hugo.toml`, add:
```bash
theme = "alpha"
```
### Method II --- Git Submodule

> This keeps Alpha **linked** to its GitHub repository, allowing you to pull updates easily.
> **Tip:** Remember to commit the `.gitmodules` file and the updated submodule reference.

1. Open your terminal and go to your site's root folder:
```bash
cd MY_HUGO_SITE
```
2. Install Alpha as a Git submodule
```bash
git submodule add https://github.com/oxypteros/alpha.git themes/alpha
```
3. Edit your `hugo.toml` and add
```bash
theme = "alpha"
```
### Method III --- Hugo Module (Requires Go)

> The most scalable approach, ideal for modular or production setups.
> **Tip:** You can override any of Alpha’s files by placing your own versions in your `layouts/`, `assets/`, `static/` folders.

1. Initialize your site as a module (if not already):
```bash
hugo mod init github.com/[YOUR_USERNAME]/[YOUR_REPOSITORY_NAME]
```
2. Add Alpha as a dependency:
```bash
hugo mod get github.com/oxypteros/alpha
```
3. Reference the theme in hugo.toml:
```bash
theme = ["github.com/oxypteros/alpha"]
```

## Troubleshoot

### No layout file
I’ve thoroughly tested all installation methods in a variety of scenarios, environments, and setups. In nearly all cases, the installation is smooth as long as there's no system misconfiguration (most commonly related to Git).

The only recurring issue I encountered was the following Hugo warning:
```bash
WARN  found no layout file for "html" for kind
```

This warning is usually caused by one of the following:
- Alpha is not installed in the correct path: It must be located exactly at `themes/alpha`.
- The `theme = "alpha"` line is missing or defined more than once in `hugo.toml`.
- If using Hugo Modules, ensure you’re using: `theme = ["github.com/oxypteros/alpha"]`.

### Module not compatible
A common warning you may see when running `hugo server` is:

```bash
WARN  Module is not compatible with this Hugo version: 0.XXX/0.XXX
```
This happens when your installed Hugo version is newer than the versions I’ve tested Alpha with. For best compatibility, Alpha uses a **minimum** and **maximum** Hugo version defined in `config/_default/hugo.toml`.

- If you’re on a version **newer** than the **recommended maximum**, Hugo will show this warning.
- In most cases, it’s harmless since Hugo rarely introduces breaking changes.
- To be extra safe, stick to the recommended maximum version until I officially test and update Alpha for newer releases.


If you encounter any other issue, please:
- Open a [GitHub issue](https://github.com/oxypteros/alpha/issues/), 
- Reach out directly from the [contact page](/contact/).

I'm happy to help!
