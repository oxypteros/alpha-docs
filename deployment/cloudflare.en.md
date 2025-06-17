+++
draft = false
date = "2025-06-04T14:43:47+02:00"
lastmod = ""
layout = "page"

title = "Cloudflare Pages"
author = "oxypteros"
license = "CC-BY-SA"
github_edit = true
series = "Alpha Docs"
  parts = "Host & Deploy"
  weight = 590
categories = ["Host & Deploy"]

recommended = false
featured = false
description = "Cloudflare Pages deployment guide for Alpha Hugo theme. Covers Git-based and direct upload methods, build configurations, environment variables and optional security headers."
# SEO
seo_type = "TechArticle"
seo_image = "cloudflare-alpha-docs-seo.png"
+++
Cloudflare Pages allows you to deploy your site by either **importing a Git repository** from *GitHub* or *GitLab*, or by using a **direct upload**.

## Deploy on Cloudflare Pages
After signing up and logging into [Cloudflare Pages](https://pages.cloudflare.com/):

1. Select **Compute (Workers)**.
2. On the *Get Started page*, choose **Pages**.
3. Decide whether to **Import an existing Git repository** or **Use direct upload**..

### Deploy from Git
1. Under *Deploy a site from your account*, choose **GitHub** or **GitLab** and connect your account.
2. After authentication, select your Alpha repository and click **Begin Setup**.

Set the following:
1. **Project name** --- This will define your site’s URL: `https://[project-name].pages.dev`
    1. In your root `hugo.toml`, set: 
      ```toml
      baseURL = "https://[project-name].pages.dev"
      ```
    2. Commit and push the change to GitHub or GitLab.
2. **Framework preset**: Choose **Hugo**
3. **Build command**:
    - With search functionality: 
    ```bash
    hugo --gc --minify && npx pagefind --site "public"
    ```
    - Without search: 
    ```bash
    hugo --gc --minify
    ```
4. **Environment variables** ( `+ Add variable`)
    - Variable name: `HUGO_VERSION`
    - Value: `0.147.7`
    **Note**: Use a `HUGO_VERSION` greater than `0.146.1`, ideally matching your local version.

Once complete, click **Save and Deploy**. 
When deployment finishes without errors, you can click **Continue to Project**.

Every consecutive push to your GitHub or GitLab repository will automatically trigger a deployment on Cloudflare Pages.

### Deploy with Direct Upload
1. From the *Get started* page on  **Compute (Workers)**,  choose **Use direct upload** and then **Get Started**.
2. Choose a **project name** (this becomes your site’s URL: `https://[project-name].pages.dev`) and click **Create Project**.
    1. In your root `hugo.toml` set`baseURL = "https://[project-name].pages.dev"` and save the change.
    2. Build your site locally:
        - With Search: 
        ```bash
        hugo --gc --minify && npx pagefind --site "public"
        ```
        - Without search: 
        ```bash
        hugo --gc --minify
        ```
        **Note**: Search requires [Node.js installed locally](/docs/developing-alpha/install-node).
3. In Cloudflare click **select from computer**, choose your local `public/` folder, and upload it.
4. Click **Deploy Site** and then **Continue to Project**.

For future updates (deployments):
1. Build your site locally.
2. Navigate to **Workers & Pages** → **`[your project name]`**.
3. Click **Create deployment** and re-upload the updated `public/` folder.

## Custom Headers File (Optional)
Alpha includes a `_headers` file preconfigured for a default Alpha installation, located at: `/themes/alpha/static/_headers`. 

This file allows you define security HTTP headers for your Cloudflare Pages deployment. Refer to the official [official documentation](https://developers.cloudflare.com/pages/configuration/headers/) for complete syntax, usage examples, and header options.

{{< status-card TITLE="Warning" TYPE="warning" >}}
Some headers (especially related to **cross-origin policies** or **Content Security Policy (CSP)**) can break your site or block third-party embeds if misconfigured. Always test your site thoroughly before going live.
{{< /status-card >}}
### How to Use
1. **Copy** the `_headers` file from `/themes/alpha/static` to your site's `static/` directory.
2. **Review** and **customize** the rules to match your site’s security and performance needs.
