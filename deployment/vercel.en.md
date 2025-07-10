+++
draft = false
date = "2025-06-05T16:31:00+02:00"
lastmod = ""
layout = "page"

title = "Vercel"
author = "oxypteros"
license = "CC-BY-SA"
github_edit = false
series = "Alpha Docs"
  parts = "Deployment"
  weight = 610
categories = ["Deployment"]

recommended = false
featured = false
description = "Vercel deployment for Alpha theme: Configure project settings, build commands, env vars, manage domains, and leverage vercel.json for advanced control."
# SEO
seo_type = "TechArticle"
seo_image = "vercel-alpha-docs-seo.png"
+++
Vercel allows deployment by **importing a Git repository** from *GitHub*, *GitLab*, *BitBucket* or *third-party platforms*.

## Deploy on Vercel
After signing up and logging into [Vercel](https://vercel.com/):

1. Choose your Git provider and install the corresponding integration if prompted.
2. Select your site’s repository and click Import.

On the **New Project** page:
1. **Project Name** --- This will be part of your deployment URL: `https://[project-name].vercel.app`

{{< status_card TITLE="Attention" TYPE="warning">}}

Vercel **does not** check for name availability during setup. If the `[project-name]` is not available, Vercel will assign a random URL like `https://[random-name].vercel.app` to your project.

{{< /status_card>}}

2. **Framework Preset**: Select **Hugo**.
3. In the **Build and Output Settings** section click the **edit icon** and set as **Build Command**:
    - With search:  
    ```bash
    hugo --gc --minify && npx pagefind --site "public"
    ```
    - Without search: 
    ```bash
    hugo --gc --minify
    ```
4. In the **Environment Variables** add:
    - Key: `HUGO_VERSION` --- Value: `0.147.7`
    **Note**: Use a `HUGO_VERSION` greater than `0.146.1`, ideally matching your local version.

5. Click **Deploy**.

Once the deployment is complete:
1. Go to your Project dashboard and click **Domains**.
2. If the default production domain matches your project name (`[project-name].vercel.app`), update your root hugo.toml: 
```toml
baseURL = "https://[project-name].vercel.app"
``` 
3. Commit and push the change to the Git Provider.

If it doesn’t match and you want a specific name:
1. Click **Add Domain**.
2. Enter a custom subdomain: `[custom-name].vercel.app`.
3. Click **Add Domain** and then **Save**.
4. After your preferred domain is added successfully:
    - **Delete** the old domain you no longer need by clicking the **three dots**.
    - Update the `baseURL` in your `hugo.toml` to reflect the new domain.
    - Push the change to the Git provider.

{{< status_card TITLE="Tip" TYPE="info">}}

If you can't **Save** due to an error go back and try using a more **specific** or **unique** name.

{{< /status_card >}}

## Vercel Json (Optional)
Vercel settings can be configured not only through the Vercel dashboard but also with a `vercel.json` file placed at the root of your project.

Alpha includes a `vercel.json` file located at: `themes/alpha/vercel.json`. The provided configuration includes security headers and a Content Security Policy (CSP) identical to those in the `themes/alpha/static/_headers` file. 

Refer to the official [Vercel JSON documentation](https://vercel.com/docs/project-configuration) for full syntax and available options.

{{< status_card TITLE="vercel.json" TYPE="info">}}

JSON does not officially support comments (even though Vercel’s parser allows them). To avoid editor validation errors, the provided `vercel.json` does not contain comments.

{{< /status_card >}}

### How to use:

1. **Copy** the file from `/themes/alpha/vercel.json` to your site's  root directory (**not** `static/`, but the actual root of your project).
2. **Review** and **customize** the rules to match your site’s security and performance needs.
