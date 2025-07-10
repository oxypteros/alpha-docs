+++
draft = false
date = "2025-06-04T12:00:50+02:00"
lastmod = ""
layout = "page"

title = "Web Analytics"
author = "oxypteros"
license = "CC-BY-SA"
github_edit = true
series = "Alpha Docs"
  parts = "Integrations"
  weight = 560
categories = ["Integrations"]

recommended = false
featured = false
description = "Integrate privacy-friendly GoatCounter analytics in Alpha. Guide covers simple setup, local script usage, opt-out features, and important considerations."
# SEO
seo_type = "TechArticle"
seo_image = "analytics-alpha-docs-seo.png"
+++
{{< status_card TITLE="Privacy" TYPE="info">}}

Discussions about **web privacy**, the pros and cons of **anonymous analytics**, or **legal compliance** with GDPR, CCPA, and similar regulations are beyond the scope of this documentation.

{{< /status_card >}}

Alpha is built with both beginners and experienced users in mind, and aims to be compliant with evolving legal standards. For these reasons (and more), Alpha follows a **zero-data** policy by default:
- No cookies
- No personal data collection
- Privacy-friendly, anonymous analytics (GoatCounter)

## GoatCounter Integration
Alpha supports integration with [GoatCounter](https://www.goatcounter.com/). A privacy-friendly, open-source web analytics platform.

GoatCounter may lack some of the advanced features of commercial alternatives, but it works well for personal websites, aligning perfectly with Alpha’s principles.

### Setup Instructions
1. **Sign up** at the [GoatCounter website](https://www.goatcounter.com/signup).
1. After signing up, your analytics dashboard will be available at:
`https://[your-code].goatcounter.com`
1. To enable GoatCounter in Alpha, add your code in `/config/_default/params.toml`:

```toml
goatcounter_prefix = "[your-code]"
```
Alpha provides a local copy of the necessary GoatCounter tracking script, so your site doesn't need to fetch it from GoatCounter's servers on every page load.

**Note**: GoatCounter **won’t work on localhost**.

### Optional Consent Features
If you enable GoatCounter, Alpha includes two optional privacy tools:
- A **cookie-free banner** (snackbar) if:
```toml
noCookies_snackbar = true
```
- An **opt-out toggle** in the visitor settings modal if:
```toml
visitor_settings = true
```
These options help ensure you're transparent with visitors and aligned with GDPR/CCPA compliance. Make sure to mention them in your privacy or policy pages.

## Other Analytics
If you prefer to use a different analytics service, you’re free to integrate it manually.
Just ensure that you inform users and remain compliant with local privacy laws and regulations.